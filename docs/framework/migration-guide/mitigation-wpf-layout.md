---
title: 'Mitigação: layout de WPF'
description: Saiba como atenuar os problemas resultantes de uma alteração no layout de controles do WPF, como o posicionamento de um objeto que se move em um pixel.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: caed758f6e86a1e2bee255c2f29ca3160b327e17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244074"
---
# <a name="mitigation-wpf-layout"></a>Mitigação: layout de WPF

O layout dos controles do WPF pode ser ligeiramente alterado.  
  
## <a name="impact"></a>Impacto  

 Como resultado dessa alteração:  
  
- A largura ou altura dos elementos pode aumentar ou reduzir em um pixel no máximo.  
  
- O posicionamento de um objeto pode ser movido até um pixel, no máximo.  
  
- Os elementos centralizados podem estar vertical ou horizontalmente fora do centro em, no máximo, um pixel.  
  
 Por padrão, esse novo layout é habilitado somente para aplicativos que se destinam ao .NET Framework 4.6.  
  
## <a name="mitigation"></a>Atenuação  

 Uma vez que essa modificação tende a eliminar a distorção da direita ou da parte inferior dos controles do WPF em DPIs altos, os aplicativos que de destinam a versões anteriores do .NET Framework, mas estão sendo executados no .NET Framework 4.6, podem aderir a esse novo comportamento adicionando a seguinte linha à seção `<runtime>` do arquivo app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Os aplicativos que se destinam ao .NET Framework 4.6, mas querem que os controles do WPF renderizem usando o algoritmo de layout anterior podem fazer isso adicionando a seguinte linha à seção `<runtime>` do arquivo app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a>Veja também

- [Compatibilidade de aplicativos](application-compatibility.md)
