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
ms.openlocfilehash: 3d9898dc6b918643aa8ca4ace34ce2e716344c57
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463495"
---
# <a name="specifiers"></a>Tanımlayıcılar
Bu konu başlığı altında açıklanır *belirticileri* (bildirim tanımlayıcıları) bileşeni bir [bildirimi](declarations-and-definitions-cpp.md).  
  
 Aşağıdaki yer tutucular ve dil anahtar sözcükleri bildirim tanımlayıcılarıdır:  
  
 *depolama sınıfı tanımlayıcısı*  
  
 *tür tanımlayıcısı*  
  
 *işlev tanımlayıcısı*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef] ( [typedef](http://msdn.microsod) `(` *genişletilmiş-decl-değiştirici-seq* `)`  
  
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