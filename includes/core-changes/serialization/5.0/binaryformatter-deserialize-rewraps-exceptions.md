---
ms.openlocfilehash: 4aef35502fc93cbf0399e3c8d0932338829d6c07
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517341"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="cd478-101">BinaryFormatter. desserializate reencapsula algumas exceções na Serializaexception</span><span class="sxs-lookup"><span data-stu-id="cd478-101">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="cd478-102">O <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> método agora reencapsula alguns objetos de exceção dentro de um <xref:System.Runtime.Serialization.SerializationException> antes de propagar a exceção de volta para o chamador.</span><span class="sxs-lookup"><span data-stu-id="cd478-102">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cd478-103">Descrição da alteração</span><span class="sxs-lookup"><span data-stu-id="cd478-103">Change description</span></span>

<span data-ttu-id="cd478-104">Anteriormente, o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> método permitia algumas exceções arbitrárias, como <xref:System.ArgumentNullException> , para propagar a pilha para seus chamadores.</span><span class="sxs-lookup"><span data-stu-id="cd478-104">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="cd478-105">No .NET 5,0 e posterior, o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> método captura de forma mais agressiva as exceções que ocorrem devido a operações de desserialização inválidas e as encapsula em um <xref:System.Runtime.Serialization.SerializationException> .</span><span class="sxs-lookup"><span data-stu-id="cd478-105">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cd478-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="cd478-106">Version introduced</span></span>

<span data-ttu-id="cd478-107">5,0 visualização 1</span><span class="sxs-lookup"><span data-stu-id="cd478-107">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cd478-108">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="cd478-108">Recommended action</span></span>

<span data-ttu-id="cd478-109">Na maioria dos casos, você não precisa realizar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="cd478-109">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="cd478-110">No entanto, se seu site de chamada depende de uma determinada exceção sendo gerada, você pode desencapsular a exceção da externa <xref:System.Runtime.Serialization.SerializationException> , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="cd478-110">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx)
{
    if (serEx.InnerException is MyException myEx)
    {
        // Handle 'myEx' here in case it was wrapped in SerializationException.
    }
    else
    {
        throw;
    }
}
```

#### <a name="category"></a><span data-ttu-id="cd478-111">Categoria</span><span class="sxs-lookup"><span data-stu-id="cd478-111">Category</span></span>

<span data-ttu-id="cd478-112">Serialização</span><span class="sxs-lookup"><span data-stu-id="cd478-112">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd478-113">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="cd478-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->