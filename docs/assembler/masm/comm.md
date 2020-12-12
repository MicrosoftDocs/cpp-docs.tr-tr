---
description: 'Daha fazla bilgi edinin: COMM'
title: COMM
ms.date: 12/06/2019
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: dc8a9ed97d55b4b6e45cb8057f46885536ba0b2f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120958"
---
# <a name="comm"></a>COMM

*Tanımda* belirtilen özniteliklere sahip bir Communal değişkeni oluşturur.

## <a name="syntax"></a>Syntax

> **Comm** *Definition* ⟦__,__ *tanım* ... ⟧

## <a name="remarks"></a>Açıklamalar

Communal değişkenleri bağlayıcı tarafından ayrılır ve başlatılamıyor. Bu, söz konusu değişkenlerin konumuna veya dizisine bağlı olamayacağı anlamına gelir.

Her *tanım* aşağıdaki biçimdedir:

⟦*Language-Type*⟧ ⟦**yakınındaki**  |  ⟧ _etiketi_**:**_Type_⟦**:**_Count_⟧

*Dil türü*, **yakın** ve **uzak** bağımsız değişkenler yalnızca 32 bitlik ması 'de geçerlidir.

İsteğe bağlı *dil türü* , aşağıdaki ad için adlandırma kurallarını ayarlar. Tarafından belirtilen tüm dilleri geçersiz kılar **. MODEL** yönergesi. İsteğe bağlı **yakın** veya **uzak** geçerli bellek modelini geçersiz kılar. *Etiket* değişkenin adıdır. *Tür* herhangi bir tür belirticisi ([byte](byte-masm.md), [Word](word.md), vb.) veya bayt sayısını belirten bir tamsayı olabilir. İsteğe bağlı *sayı* , belirtilen veri nesnesindeki öğelerin sayısını belirtir. Varsayılan *sayı* bir.

## <a name="example"></a>Örnek

Bu örnek, 512 BAYTLıK öğelerin bir dizisini oluşturur:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
