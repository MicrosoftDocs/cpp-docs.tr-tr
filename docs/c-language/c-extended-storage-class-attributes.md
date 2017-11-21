---
title: "C genişletilmiş depolama sınıfı öznitelikler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 119de1e705a0e3de93aadc61d38ecdde2fc43fe9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-extended-storage-class-attributes"></a>C Genişletilmiş Depolama Sınıfı Öznitelikler
**Microsoft özel**  
  
 Bu konu hakkında daha fazla güncel bilgi altında bulunabilir [__declspec (C++ başvuru)](../cpp/declspec.md).  
  
 Genişletilmiş öznitelik sözdizimi, C diline yönelik Microsoft'a özel uzantıları basitleştirir ve standartlaştırır. Genişletilmiş öznitelik sözdizimini kullanın depolama sınıfı öznitelikler, iş parçacığı, çıplak, dllimport ve dllexport'u içerir.  
  
 Depolama sınıfı bilgilerini belirtmeye yönelik genişletilmiş öznitelik sözdizimi __declspec anahtar sözcüğünü kullanır; bu anahtar sözcük belirli bir türden örneğin aşağıda listelenen Microsoft'a özgü depolama sınıfı özniteliğiyle (thread, naked, dllimport veya dllexport) depolanması gerektiğini belirtir. Diğer depolama sınıfı değiştiricilere yönelik örnekler, static ve extern anahtar sözcüklerini içerir. Ancak, bu anahtar sözcükler ANSI C standardının bir parçasıdır ve bunlar genişletilmiş öznitelik sözdiziminin kapsamına girmez.  
  
## <a name="syntax"></a>Sözdizimi  
 *depolama sınıfı tanımlayıcısı*:  
 `__declspec`( *genişletilmiş-decl-değiştirici-seq* ) / * Microsoft Specific\*/  
  
 *Genişletilmiş-decl-değiştirici-seq*:  
 *Genişletilmiş decl-değiştirici* iptal et  
  
 *Genişletilmiş-decl-değiştirici-seq genişletilmiş decl-değiştirici*  
  
 *Genişletilmiş decl-değiştirici*:  
 **iş parçacığı**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 Boşluk, bildirim değiştiricilerini ayırır. Unutmayın *genişletilmiş-decl-değiştirici-seq* boş olabilir; bu durumda, __declspec hiçbir etkisi olmaz.  
  
 İş parçacığı, çıplak, dllimport ve dllexport depolama sınıfı öznitelikleri, yalnızca uygulandıkları veri veya işlevin bildiriminin özelliğidir; işlevin tür özniteliklerini yeniden tanımlamazlar. İş parçacığı özniteliği yalnızca verileri etkiler. Çıplak özniteliği yalnızca işlevleri etkiler. dllimport ve dllexport öznitelikleri işlevleri ve verileri etkiler.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve türler](../c-language/declarations-and-types.md)