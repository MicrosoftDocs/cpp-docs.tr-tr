---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1179'
title: Bağlayıcı Araçları Hatası LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: 691476eeffadece2436518c5249ca523adca51c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253448"
---
# <a name="linker-tools-error-lnk1179"></a>Bağlayıcı Araçları Hatası LNK1179

dosya geçersiz veya bozuk: yinelenen COMDAT ' filename '

Bir nesne modülü aynı ada sahip iki veya daha fazla Comtts içeriyor.

Bu hata, dış adların uzunluğunu sınırlayan ve [/GY](../../build/reference/gy-enable-function-level-linking.md)' nin, Comcts 'de işlev gören [/h](../../build/reference/h-restrict-length-of-external-names.md)kullanılarak kaynaklanıyor olabilir.

## <a name="example"></a>Örnek

Aşağıdaki kodda, `function1` ve `function2` ilk sekiz karakterle aynıdır. **/GY** ve **/H8** ile derleme bir bağlantı hatası oluşturur.

```cpp
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```
