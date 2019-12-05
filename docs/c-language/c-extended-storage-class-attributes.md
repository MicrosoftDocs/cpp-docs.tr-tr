---
title: C Genişletilmiş Depolama Sınıfı Öznitelikler
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
ms.openlocfilehash: c2e372ebe93b9240ac6f489e8b1aefc1fbbded80
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857157"
---
# <a name="c-extended-storage-class-attributes"></a>C Genişletilmiş Depolama Sınıfı Öznitelikler

**Microsoft 'a özgü**

Bu konuyla ilgili daha güncel bilgiler, [__declspec (C++ başvuru)](../cpp/declspec.md)altında bulunabilir.

Genişletilmiş öznitelik sözdizimi, C diline yönelik Microsoft'a özel uzantıları basitleştirir ve standartlaştırır. Genişletilmiş öznitelik sözdizimini kullanın depolama sınıfı öznitelikler, iş parçacığı, çıplak, dllimport ve dllexport'u içerir.

Depolama sınıfı bilgilerini belirtmeye yönelik genişletilmiş öznitelik sözdizimi __declspec anahtar sözcüğünü kullanır; bu anahtar sözcük belirli bir türden örneğin aşağıda listelenen Microsoft'a özgü depolama sınıfı özniteliğiyle (thread, naked, dllimport veya dllexport) depolanması gerektiğini belirtir. Diğer depolama sınıfı değiştiricilere yönelik örnekler, static ve extern anahtar sözcüklerini içerir. Ancak, bu anahtar sözcükler ANSI C standardının bir parçasıdır ve bunlar genişletilmiş öznitelik sözdiziminin kapsamına girmez.

## <a name="syntax"></a>Sözdizimi

*depolama sınıfı Belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *Genişletilmiş-decl-değiştirici-seq* **)**  /\* Microsoft 'a özgü \*/

*Genişletilmiş-decl-Modifier-Seq*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-Modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici-seq* *Extended-decl-değiştiricisi*

*Extended-decl-değiştirici*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**iş parçacığı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

Boşluk, bildirim değiştiricilerini ayırır. *Genişletilmiş-decl-değiştirici-seq* ' in boş olabileceğini unutmayın; Bu durumda __declspec hiçbir etkisi yoktur.

İş parçacığı, çıplak, dllimport ve dllexport depolama sınıfı öznitelikleri, yalnızca uygulandıkları veri veya işlevin bildiriminin özelliğidir; işlevin tür özniteliklerini yeniden tanımlamazlar. İş parçacığı özniteliği yalnızca verileri etkiler. Çıplak özniteliği yalnızca işlevleri etkiler. dllimport ve dllexport öznitelikleri işlevleri ve verileri etkiler.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)
