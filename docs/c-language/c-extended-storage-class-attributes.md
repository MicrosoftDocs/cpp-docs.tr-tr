---
description: 'Daha fazla bilgi edinin: C genişletilmiş Storage-Class öznitelikleri'
title: C Genişletilmiş Depolama Sınıfı Öznitelikler
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
ms.openlocfilehash: 9dff43594ef97214609c6ed2195240d0e21648e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168767"
---
# <a name="c-extended-storage-class-attributes"></a>C Genişletilmiş Depolama Sınıfı Öznitelikler

**Microsoft'a Özgü**

Bu konuyla ilgili daha güncel bilgiler, [__declspec (C++ Başvurusu)](../cpp/declspec.md)altında bulunabilir.

Genişletilmiş öznitelik sözdizimi, C diline yönelik Microsoft'a özel uzantıları basitleştirir ve standartlaştırır. Genişletilmiş öznitelik sözdizimini kullanın depolama sınıfı öznitelikler, iş parçacığı, çıplak, dllimport ve dllexport'u içerir.

Depolama sınıfı bilgilerini belirtmeye yönelik genişletilmiş öznitelik sözdizimi __declspec anahtar sözcüğünü kullanır; bu anahtar sözcük belirli bir türden örneğin aşağıda listelenen Microsoft'a özgü depolama sınıfı özniteliğiyle (thread, naked, dllimport veya dllexport) depolanması gerektiğini belirtir. Diğer depolama sınıfı değiştiricilere yönelik örnekler, static ve extern anahtar sözcüklerini içerir. Ancak, bu anahtar sözcükler ANSI C standardının bir parçasıdır ve bunlar genişletilmiş öznitelik sözdiziminin kapsamına girmez.

## <a name="syntax"></a>Syntax

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
