---
title: C genişletilmiş depolama sınıfı öznitelikler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a55f4ac98a712d8166c3d0ca5e22e13cb8c9145
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758823"
---
# <a name="c-extended-storage-class-attributes"></a>C Genişletilmiş Depolama Sınıfı Öznitelikler
**Microsoft'a özgü**  
  
Bu konu hakkında daha fazla güncel bilgi altında bulunabilir [__declspec (C++ Başvurusu)](../cpp/declspec.md).  
  
Genişletilmiş öznitelik sözdizimi, C diline yönelik Microsoft'a özel uzantıları basitleştirir ve standartlaştırır. Genişletilmiş öznitelik sözdizimini kullanın depolama sınıfı öznitelikler, iş parçacığı, çıplak, dllimport ve dllexport'u içerir.  
  
Depolama sınıfı bilgilerini belirtmeye yönelik genişletilmiş öznitelik sözdizimi __declspec anahtar sözcüğünü kullanır; bu anahtar sözcük belirli bir türden örneğin aşağıda listelenen Microsoft'a özgü depolama sınıfı özniteliğiyle (thread, naked, dllimport veya dllexport) depolanması gerektiğini belirtir. Diğer depolama sınıfı değiştiricilere yönelik örnekler, static ve extern anahtar sözcüklerini içerir. Ancak, bu anahtar sözcükler ANSI C standardının bir parçasıdır ve bunlar genişletilmiş öznitelik sözdiziminin kapsamına girmez.  
  
## <a name="syntax"></a>Sözdizimi

*depolama sınıfı tanımlayıcısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (** *genişletilmiş-decl-değiştirici-seq* **)**  / \* Microsoft Specific \*/

*Genişletilmiş-decl-değiştirici-seq*:&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici-seq* *genişletilmiş-decl-değiştirici*

*Genişletilmiş-decl-değiştirici*:&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**iş parçacığı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

Boşluk, bildirim değiştiricilerini ayırır. Unutmayın *genişletilmiş-decl-değiştirici-seq* boş olabilir; bu durumda, __declspec etkisi yoktur.
  
İş parçacığı, çıplak, dllimport ve dllexport depolama sınıfı öznitelikleri, yalnızca uygulandıkları veri veya işlevin bildiriminin özelliğidir; işlevin tür özniteliklerini yeniden tanımlamazlar. İş parçacığı özniteliği yalnızca verileri etkiler. Çıplak özniteliği yalnızca işlevleri etkiler. dllimport ve dllexport öznitelikleri işlevleri ve verileri etkiler.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Bildirimler ve Türler](../c-language/declarations-and-types.md)