---
title: Extensão de marcação x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072042"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="b0056-102">Extensão de marcação x:Array</span><span class="sxs-lookup"><span data-stu-id="b0056-102">x:Array Markup Extension</span></span>

<span data-ttu-id="b0056-103">Fornece suporte geral para matrizes de objetos em XAML através de uma extensão de marcação.</span><span class="sxs-lookup"><span data-stu-id="b0056-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="b0056-104">Isso corresponde ao `x:ArrayExtension` tipo XAML em [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="b0056-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="b0056-105">Uso de elemento Object do XAML</span><span class="sxs-lookup"><span data-stu-id="b0056-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="b0056-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="b0056-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="b0056-107">O nome do tipo `x:Array` que seu testamento conterá.</span><span class="sxs-lookup"><span data-stu-id="b0056-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="b0056-108">`typeName`pode ser (e muitas vezes é) prefixado para um namespace XAML que contém as definições do tipo XAML.</span><span class="sxs-lookup"><span data-stu-id="b0056-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="b0056-109">O conteúdo dos itens atribuídos à propriedade `ArrayExtension.Items` intrínseca.</span><span class="sxs-lookup"><span data-stu-id="b0056-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="b0056-110">Normalmente, esses itens são especificados como um ou `x:Array` mais elementos de objeto contidos nas tags de abertura e fechamento.</span><span class="sxs-lookup"><span data-stu-id="b0056-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="b0056-111">Espera-se que os objetos especificados aqui sejam atribuídos `typeName`ao tipo XAML especificado em .</span><span class="sxs-lookup"><span data-stu-id="b0056-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b0056-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="b0056-112">Remarks</span></span>

<span data-ttu-id="b0056-113">`Type`é um atributo `x:Array` necessário para todos os elementos do objeto.</span><span class="sxs-lookup"><span data-stu-id="b0056-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="b0056-114">Um `Type` valor de parâmetro não `x:Type` precisa usar uma extensão de marcação; o nome curto do tipo é um tipo XAML, que pode ser especificado como uma string.</span><span class="sxs-lookup"><span data-stu-id="b0056-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="b0056-115">Na implementação do .NET XAML Services, a relação entre <xref:System.Type> o tipo XAML de entrada e a CLR de saída do array criado é influenciada pelo contexto de serviço para extensões de marcação.</span><span class="sxs-lookup"><span data-stu-id="b0056-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="b0056-116">A <xref:System.Type> saída <xref:System.Xaml.XamlType.UnderlyingType%2A> é do tipo XAML de entrada, depois de procurar o <xref:System.Xaml.XamlType> necessário <xref:System.Windows.Markup.IXamlTypeResolver> com base no contexto do esquema XAML e no serviço que o contexto fornece.</span><span class="sxs-lookup"><span data-stu-id="b0056-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="b0056-117">Quando processado, o conteúdo da matriz `ArrayExtension.Items` é atribuído à propriedade intrínseca.</span><span class="sxs-lookup"><span data-stu-id="b0056-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="b0056-118">Na <xref:System.Windows.Markup.ArrayExtension> implementação, isso <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>é representado por .</span><span class="sxs-lookup"><span data-stu-id="b0056-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b0056-119">Na implementação do .NET XAML Services, o manuseio <xref:System.Windows.Markup.ArrayExtension> dessa extensão de marcação é definido pela classe.</span><span class="sxs-lookup"><span data-stu-id="b0056-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="b0056-120"><xref:System.Windows.Markup.ArrayExtension>não é selado e pode ser usado como base para uma implementação de extensão de marcação para um tipo de array personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0056-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="b0056-121">`x:Array`é mais destinado à extensibilidade geral da linguagem em XAML.</span><span class="sxs-lookup"><span data-stu-id="b0056-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="b0056-122">Mas `x:Array` também pode ser útil para especificar valores XAML de certas propriedades que tomam coleções suportadas por XAML como seu conteúdo de propriedade estruturado.</span><span class="sxs-lookup"><span data-stu-id="b0056-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="b0056-123">Por exemplo, você pode especificar o conteúdo de uma <xref:System.Collections.IEnumerable> propriedade com um `x:Array` uso.</span><span class="sxs-lookup"><span data-stu-id="b0056-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="b0056-124">`x:Array` é uma extensão da marcação.</span><span class="sxs-lookup"><span data-stu-id="b0056-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="b0056-125">Extensões de marcação são tipicamente implementadas quando existe um requisito que permite que valores de atributo sejam diferentes de valores literais ou nomes de manipuladores, e o requisito é mais global do que simplesmente colocar conversores de tipo em certos tipos ou propriedades.</span><span class="sxs-lookup"><span data-stu-id="b0056-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="b0056-126">`x:Array`é parcialmente uma exceção a essa regra porque, `x:Array` em vez de fornecer tratamento alternativo de valor de atributo, fornece tratamento alternativo de seu conteúdo de texto interno.</span><span class="sxs-lookup"><span data-stu-id="b0056-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="b0056-127">Esse comportamento permite que tipos que podem não ser suportados por um modelo de conteúdo existente sejam agrupados em uma matriz e referenciados posteriormente no code-behind acessando a matriz nomeada; você pode <xref:System.Array> chamar métodos para obter itens de matriz individuais.</span><span class="sxs-lookup"><span data-stu-id="b0056-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="b0056-128">Todas as extensões de marcação em{,} `)` XAML usam os aparelhos ( em sua sintaxe de atributo, que é a convenção pela qual um processador XAML reconhece que uma extensão de marcação deve processar o valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="b0056-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="b0056-129">Para obter mais informações sobre extensões de marcação em geral, consulte [Type Converters e Extensões de Marcação para XAML](type-converters-and-markup-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="b0056-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="b0056-130">No XAML 2009, `x:Array` é definido como uma linguagem primitiva em vez de uma extensão de marcação.</span><span class="sxs-lookup"><span data-stu-id="b0056-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="b0056-131">Para obter mais informações, consulte [Tipos incorporados para primitivos comuns da linguagem XAML](types-for-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="b0056-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="b0056-132">Notas de uso do WPF</span><span class="sxs-lookup"><span data-stu-id="b0056-132">WPF Usage Notes</span></span>

<span data-ttu-id="b0056-133">Normalmente, os elementos `x:Array` do objeto que povoam um não são elementos que existem no namespace [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML e requerem um mapeamento de prefixo para um namespace XAML não padrão.</span><span class="sxs-lookup"><span data-stu-id="b0056-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="b0056-134">Por exemplo, o seguinte é uma matriz simples `sys` de duas `x`strings, com o prefixo (e também ) definido no nível da matriz.</span><span class="sxs-lookup"><span data-stu-id="b0056-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="b0056-135">Para tipos personalizados que são usados como elementos de matriz, a classe também deve suportar os requisitos para ser instanciado em XAML como elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="b0056-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="b0056-136">Para obter mais informações, consulte [XAML e Classes Personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="b0056-136">For more information, see [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b0056-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="b0056-137">See also</span></span>

- [<span data-ttu-id="b0056-138">Extensões de marcação e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="b0056-138">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="b0056-139">Tipos migrados do WPF para System.Xaml</span><span class="sxs-lookup"><span data-stu-id="b0056-139">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)