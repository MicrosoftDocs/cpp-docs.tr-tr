---
title: Tanımlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c1fb739d5e6206297e52fd9103cbba98c5eef01
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42465295"
---
# <a name="specifiers"></a>Tanımlayıcılar
Bu konu başlığı altında açıklanır *belirticileri* (bildirim tanımlayıcıları) bileşeni bir [bildirimi](declarations-and-definitions-cpp.md).  
  
 Aşağıdaki yer tutucular ve dil anahtar sözcükleri bildirim tanımlayıcılarıdır:  
  
 *depolama sınıfı tanımlayıcısı*  
  
 *tür tanımlayıcısı*  
  
 *işlev tanımlayıcısı*  
  
 [friend](friend-cpp.md)  
 
 [TypeDef](aliases-and-typedefs-cpp.md) `(` *genişletilmiş-decl-değiştirici-seq* `)`  

 [__declspec](declspec.md) `(` *genişletilmiş-decl-değiştirici-seq* `)`  
  
## <a name="remarks"></a>Açıklamalar  
 *Belirticileri* parçasıdır bir bildirimin en uzun dizi *belirticileri* işaretçi içermeden bir tür adını veya başvuru değiştiricilerini alınabilmesini. Bildirimin geri kalanı olan *bildirimci*, sunulan adı içeren.  
  
 Aşağıdaki tabloda dört bildirim listelenmekte ve ardından her bildirimin listeler *decl-specifers* ve *bildirimci* bileşeni ayrı ayrı.  
  
|Bildirim|*belirticileri*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|**char**|`*lpszAppName`|  
|`typedef char * LPSTR;`|**char**|`*LPSTR`|  
|`const int func1();`|**const int**|`func1`|  
|`volatile void *pvvObj;`|**geçici bir geçersiz kılma**|`*pvvObj`|  
  
 Çünkü **imzalı**, **işaretsiz**, **uzun**, ve **kısa** tüm yaptığından **int**,  **TypeDef** adı bu anahtar sözcüklerden biri üye olmasını alınır *bildirimci listesi* değil *belirticileri*.  
  
> [!NOTE]
>  Bir ad tekrar bildirilebileceğinden, yorumlanması geçerli kapsamdaki en yeni bildirime göre yapılır. Yeniden bildirimi adlar derleyici tarafından özellikle yorumlanma şeklini etkileyebilir **typedef** adları.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)
