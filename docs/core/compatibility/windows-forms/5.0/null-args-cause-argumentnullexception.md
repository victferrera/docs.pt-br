---
title: 'Alteração significativa: os métodos do WinForms agora lançam ArgumentNullException'
description: Saiba mais sobre a alteração significativa no .NET 5,0, em que alguns métodos de Windows Forms agora lançam um ArgumentNullException para argumentos nulos.
ms.date: 09/18/2020
ms.openlocfilehash: 77280827d44b0e58533339a09357d518a0bfe508
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760492"
---
# <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="89c80-103">Os métodos WinForms agora lançam ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="89c80-103">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="89c80-104">Alguns métodos de Windows Forms agora geram um <xref:System.ArgumentNullException> para argumentos nulos, onde anteriormente eles lançavam um <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="89c80-104">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

## <a name="change-description"></a><span data-ttu-id="89c80-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="89c80-105">Change description</span></span>

<span data-ttu-id="89c80-106">Anteriormente, determinados métodos de Windows Forms lançavam um <xref:System.NullReferenceException> se passasse um argumento que era nulo.</span><span class="sxs-lookup"><span data-stu-id="89c80-106">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="89c80-107">A partir do .NET 5,0, esses métodos agora geram um <xref:System.ArgumentNullException> para argumentos nulos, em vez disso.</span><span class="sxs-lookup"><span data-stu-id="89c80-107">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="89c80-108">Lançar um <xref:System.ArgumentNullException> está em conformidade com o comportamento do tempo de execução do .net.</span><span class="sxs-lookup"><span data-stu-id="89c80-108">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="89c80-109">Ele também melhora a experiência de depuração, comunicando claramente que um argumento é nulo e qual é o argumento.</span><span class="sxs-lookup"><span data-stu-id="89c80-109">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="89c80-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="89c80-110">Version introduced</span></span>

<span data-ttu-id="89c80-111">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="89c80-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="89c80-112">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="89c80-112">Recommended action</span></span>

<span data-ttu-id="89c80-113">Se você chamar qualquer um desses métodos e o seu código atualmente capturar um <xref:System.NullReferenceException> para argumentos nulos, pegue um <xref:System.ArgumentNullException> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="89c80-113">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="89c80-114">Além disso, considere atualizar o código para evitar a passagem de argumentos nulos para os métodos listados.</span><span class="sxs-lookup"><span data-stu-id="89c80-114">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="89c80-115">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="89c80-115">Affected APIs</span></span>

<span data-ttu-id="89c80-116">A tabela a seguir lista os métodos e parâmetros afetados:</span><span class="sxs-lookup"><span data-stu-id="89c80-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="89c80-117">Método</span><span class="sxs-lookup"><span data-stu-id="89c80-117">Method</span></span> | <span data-ttu-id="89c80-118">Nome do parâmetro</span><span class="sxs-lookup"><span data-stu-id="89c80-118">Parameter name</span></span> | <span data-ttu-id="89c80-119">Versão adicionada</span><span class="sxs-lookup"><span data-stu-id="89c80-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="89c80-120">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-120">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="89c80-121">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-121">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="89c80-122">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-122">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="89c80-123">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-123">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="89c80-124">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-124">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="89c80-125">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-125">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="89c80-126">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-126">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="89c80-127">Preview 1</span><span class="sxs-lookup"><span data-stu-id="89c80-127">Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="89c80-128">Preview 2</span><span class="sxs-lookup"><span data-stu-id="89c80-128">Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="89c80-129">Preview 2</span><span class="sxs-lookup"><span data-stu-id="89c80-129">Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="89c80-130">Versão prévia 5</span><span class="sxs-lookup"><span data-stu-id="89c80-130">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="89c80-131">Versão prévia 5</span><span class="sxs-lookup"><span data-stu-id="89c80-131">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="89c80-132">Versão prévia 5</span><span class="sxs-lookup"><span data-stu-id="89c80-132">Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="89c80-133">Versão prévia 5</span><span class="sxs-lookup"><span data-stu-id="89c80-133">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="89c80-134">Versão prévia 6</span><span class="sxs-lookup"><span data-stu-id="89c80-134">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="89c80-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="89c80-135">`owner`, `value`</span></span> | <span data-ttu-id="89c80-136">Versão prévia 6</span><span class="sxs-lookup"><span data-stu-id="89c80-136">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="89c80-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="89c80-137">`owner`, `value`</span></span> | <span data-ttu-id="89c80-138">Versão prévia 6</span><span class="sxs-lookup"><span data-stu-id="89c80-138">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="89c80-139">Versão prévia 6</span><span class="sxs-lookup"><span data-stu-id="89c80-139">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="89c80-140">Versão prévia 6</span><span class="sxs-lookup"><span data-stu-id="89c80-140">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="89c80-141">Versão prévia 6</span><span class="sxs-lookup"><span data-stu-id="89c80-141">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="89c80-142">Versão prévia 6</span><span class="sxs-lookup"><span data-stu-id="89c80-142">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListView.SelectedIndexCollection.%23ctor(System.Windows.Forms.ListView)> | `owner` | <span data-ttu-id="89c80-143">Versão prévia 7</span><span class="sxs-lookup"><span data-stu-id="89c80-143">Preview 7</span></span> |
> | <xref:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="89c80-144">`key` está `null` ou vazio</span><span class="sxs-lookup"><span data-stu-id="89c80-144">`key` is `null` or empty</span></span> | <span data-ttu-id="89c80-145">Visualização 8</span><span class="sxs-lookup"><span data-stu-id="89c80-145">Preview 8</span></span> |
> | <xref:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="89c80-146">`key` está `null` ou vazio</span><span class="sxs-lookup"><span data-stu-id="89c80-146">`key` is `null` or empty</span></span> | <span data-ttu-id="89c80-147">RC1</span><span class="sxs-lookup"><span data-stu-id="89c80-147">RC1</span></span> |
> | <xref:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="89c80-148">RC1</span><span class="sxs-lookup"><span data-stu-id="89c80-148">RC1</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`
- `M:System.Windows.Forms.ListViewGroup.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.#ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System#Collections#ICollection#CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListView.SelectedIndexCollection.#ctor(System.Windows.Forms.ListView)`
- `M:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)`

### Category

Windows Forms

-->