---
title: COMM
ms.date: 08/30/2018
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: d36161ba54ca80fc0f576c6f0a7c2a9410bf8075
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541030"
---
# <a name="comm"></a>COMM

*Tanımda*belirtilen özniteliklere sahip bir Communal değişkeni oluşturur.

## <a name="syntax"></a>Sözdizimi

> **Comm** *Definition* ⟦ __,__ *tanım* ... ⟧

## <a name="remarks"></a>Açıklamalar

Communal değişkenleri bağlayıcı tarafından ayrılır ve başlatılamıyor. Bu, söz konusu değişkenlerin konumuna veya dizisine bağlı olamayacağı anlamına gelir.

Her *tanım* aşağıdaki biçimdedir:

⟦*Language-Type*⟧ ⟦**yakınındaki** | **Far**⟧ _etiketi_ **:** _Type_⟦ **:** _Count_⟧

İsteğe bağlı *dil türü* , aşağıdaki ad için adlandırma kurallarını ayarlar. Tarafından belirtilen tüm dilleri geçersiz kılar **. MODEL** yönergesi. İsteğe bağlı **yakın** veya **uzak** geçerli bellek modelini geçersiz kılar. *Etiket* değişkenin adıdır. *Tür* herhangi bir tür belirticisi ([byte](../../assembler/masm/byte-masm.md), [Word](../../assembler/masm/word.md), vb.) veya bayt sayısını belirten bir tamsayı olabilir. İsteğe bağlı *sayı* , belirtilen veri nesnesindeki öğelerin sayısını belirtir. Varsayılan *sayı* bir.

## <a name="example"></a>Örnek

Bu örnek, 512 BAYTLıK öğelerin bir dizisini oluşturur:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
