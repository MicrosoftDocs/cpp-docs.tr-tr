---
title: Bağlayıcı Araçları Hatası LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: 71aba1f20cfaf5b6b9ec33d43ebde594e381921f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391419"
---
# <a name="linker-tools-error-lnk1179"></a>Bağlayıcı Araçları Hatası LNK1179

dosya geçersiz veya bozuk: Yinelenen COMDAT 'filename'

İki veya daha fazla comdat'ları aynı ada sahip bir nesne modülü içerir.

Kullanarak bu hata oluşabilir [/H](../../build/reference/h-restrict-length-of-external-names.md), dış adların uzunluğunu kısıtlar ve [/Gy](../../build/reference/gy-enable-function-level-linking.md), comdat'ları işlevlerde paketler.

## <a name="example"></a>Örnek

Aşağıdaki kodda, `function1` ve `function2` ilk sekiz karakterini içinde aynıdır. İle derlerken **/Gy** ve **/H8** bir bağlantı hatası oluşturur.

```
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```