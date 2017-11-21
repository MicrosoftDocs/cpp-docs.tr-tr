---
title: "Tanımlayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2a242c2c517f7db6f75b825bd13396637a64d138
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="specifiers"></a>Tanımlayıcılar
Bu konuda açıklanmaktadır *decl tanımlayıcıları* (bildirim tanımlayıcıları) bileşeninin bir [bildirimi](declarations-and-definitions-cpp.md).  
  
 Aşağıdaki yer tutucular ve dil anahtar sözcükleri bildirim tanımlayıcılarıdır:  
  
 *depolama sınıfı tanımlayıcısı*  
  
 *tür tanımlayıcısı*  
  
 *işlevi belirleyici*  
  
 [arkadaş](../cpp/friend-cpp.md)  
  
 [TypeDef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [__declspec](../cpp/declspec.md) `(` *genişletilmiş-decl-değiştirici-seq*`)`  
  
## <a name="remarks"></a>Açıklamalar  
 *Decl tanımlayıcıları* bir bildirimi parçası olan uzun bir dizi *decl tanımlayıcıları* işaretçinin dahil olmayan bir tür adını anlamına veya değiştiricileri başvuru alınabilmesini. Kalan bildirimiyle *bildirimcisi*, sunulan adını içerir.  
  
 Aşağıdaki tabloda dört bildirimleri listeler ve her bildirim 's listeler *decl specifers* ve *bildirimcisi* bileşen ayrı olarak.  
  
|Bildirim|*Decl tanımlayıcıları*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 Çünkü `signed`, `unsigned`, `long`, ve `short` tüm kapsıyor `int`, `typedef` şu anahtar sözcüklerden biri gerçekleştirilecek bir üyesi olması için aşağıdaki ad *bildirimcisi listesi,* ,değil*decl tanımlayıcıları*.  
  
> [!NOTE]
>  Bir ad tekrar bildirilebileceğinden, yorumlanması geçerli kapsamdaki en yeni bildirime göre yapılır. Tekrar bildirme, adların (özellikle `typedef` adları) derleyici tarafından yorumlanma şeklini etkileyebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve tanımlar](declarations-and-definitions-cpp.md)