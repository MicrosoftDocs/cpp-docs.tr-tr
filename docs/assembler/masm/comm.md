---
title: COMM
ms.date: 12/06/2019
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: 93e7c891b1c964eca5b3ff7fd15956ef25ea05e6
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987947"
---
# <a name="comm"></a>COMM

*Tanımda*belirtilen özniteliklere sahip bir Communal değişkeni oluşturur.

## <a name="syntax"></a>Sözdizimi

> **Comm** *Definition* ⟦ __,__ *tanım* ... ⟧

## <a name="remarks"></a>Açıklamalar

Communal değişkenleri bağlayıcı tarafından ayrılır ve başlatılamıyor. Bu, söz konusu değişkenlerin konumuna veya dizisine bağlı olamayacağı anlamına gelir.

Her *tanım* aşağıdaki biçimdedir:

⟦*Language-Type*⟧ ⟦**yakınındaki** | **Far**⟧ _etiketi_ **:** _Type_⟦ **:** _Count_⟧

*Dil türü*, **yakın**ve **uzak** bağımsız değişkenler yalnızca 32 bitlik ması 'de geçerlidir.

İsteğe bağlı *dil türü* , aşağıdaki ad için adlandırma kurallarını ayarlar. Tarafından belirtilen tüm dilleri geçersiz kılar **. MODEL** yönergesi. İsteğe bağlı **yakın** veya **uzak** geçerli bellek modelini geçersiz kılar. *Etiket* değişkenin adıdır. *Tür* herhangi bir tür belirticisi ([byte](../../assembler/masm/byte-masm.md), [Word](../../assembler/masm/word.md), vb.) veya bayt sayısını belirten bir tamsayı olabilir. İsteğe bağlı *sayı* , belirtilen veri nesnesindeki öğelerin sayısını belirtir. Varsayılan *sayı* bir.

## <a name="example"></a>Örnek

Bu örnek, 512 BAYTLıK öğelerin bir dizisini oluşturur:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
