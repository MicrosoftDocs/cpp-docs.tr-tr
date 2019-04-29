---
title: Tanımlayıcılar
ms.date: 11/04/2016
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
ms.openlocfilehash: aef967b26321f289cb8c7bd0402d7fe8f12b77b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330992"
---
# <a name="specifiers"></a>Tanımlayıcılar

Bu konu başlığı altında açıklanır *belirticileri* (bildirim tanımlayıcıları) bileşeni bir [bildirimi](declarations-and-definitions-cpp.md).

Aşağıdaki yer tutucular ve dil anahtar sözcükleri bildirim tanımlayıcılarıdır:

*depolama sınıfı tanımlayıcısı*

*tür tanımlayıcısı*

*işlev tanımlayıcısı*

[friend](friend-cpp.md)

[typedef](aliases-and-typedefs-cpp.md) `(` *extended-decl-modifier-seq* `)`

[__declspec](declspec.md) `(` *extended-decl-modifier-seq* `)`

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
