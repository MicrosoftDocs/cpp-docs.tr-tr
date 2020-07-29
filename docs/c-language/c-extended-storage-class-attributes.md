---
title: C Genişletilmiş Depolama Sınıfı Öznitelikler
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
ms.openlocfilehash: 5e1fe80f3bc1f581c6ea05c54409b1e76eacfce7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87190227"
---
# <a name="c-extended-storage-class-attributes"></a>C Genişletilmiş Depolama Sınıfı Öznitelikler

**Microsoft'a Özgü**

Bu konuyla ilgili daha güncel bilgiler, [__declspec (C++ Başvurusu)](../cpp/declspec.md)altında bulunabilir.

Genişletilmiş öznitelik sözdizimi, C diline yönelik Microsoft'a özel uzantıları basitleştirir ve standartlaştırır. Genişletilmiş öznitelik sözdizimini kullanın depolama sınıfı öznitelikler, iş parçacığı, çıplak, dllimport ve dllexport'u içerir.

Depolama sınıfı bilgilerini belirtmeye yönelik genişletilmiş öznitelik sözdizimi __declspec anahtar sözcüğünü kullanır; bu anahtar sözcük belirli bir türden örneğin aşağıda listelenen Microsoft'a özgü depolama sınıfı özniteliğiyle (thread, naked, dllimport veya dllexport) depolanması gerektiğini belirtir. Diğer depolama sınıfı değiştiricilere yönelik örnekler, static ve extern anahtar sözcüklerini içerir. Ancak, bu anahtar sözcükler ANSI C standardının bir parçasıdır ve bunlar genişletilmiş öznitelik sözdiziminin kapsamına girmez.

## <a name="syntax"></a>Sözdizimi

*depolama sınıfı Belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (** *Genişletilmiş-decl-değiştirici-seq* **)**  / \* Microsoft 'a özgü\*/

*Extended-decl-değiştirici-seq*: &nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Extended-decl-değiştirici*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Extended-decl-değiştirici-seq* *Extended-decl-değiştiricisi*

*Extended-decl-değiştirici*: &nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`thread`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`naked`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`dllimport`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`dllexport`**

Boşluk, bildirim değiştiricilerini ayırır. *Genişletilmiş-decl-değiştirici-seq* ' in boş olabileceğini unutmayın; Bu durumda __declspec hiçbir etkisi yoktur.

İş parçacığı, çıplak, dllimport ve dllexport depolama sınıfı öznitelikleri, yalnızca uygulandıkları veri veya işlevin bildiriminin özelliğidir; işlevin tür özniteliklerini yeniden tanımlamazlar. İş parçacığı özniteliği yalnızca verileri etkiler. Çıplak özniteliği yalnızca işlevleri etkiler. dllimport ve dllexport öznitelikleri işlevleri ve verileri etkiler.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
