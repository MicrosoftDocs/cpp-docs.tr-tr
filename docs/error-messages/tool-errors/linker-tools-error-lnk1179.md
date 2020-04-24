---
title: Bağlayıcı Araçları Hatası LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: d85693cec11ef53a6bbbb60d8ced716d2a0bb131
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754341"
---
# <a name="linker-tools-error-lnk1179"></a>Bağlayıcı Araçları Hatası LNK1179

geçersiz veya bozuk dosya: yinelenen COMDAT 'dosya adı'

Nesne modülü aynı ada sahip iki veya daha fazla COMDAt içerir.

Bu hata, dış adların uzunluğunu sınırlayan [/H](../../build/reference/h-restrict-length-of-external-names.md)ve COMDAT'larda işlevleri paketler [/Gy'nin](../../build/reference/gy-enable-function-level-linking.md)kullanılmasından kaynaklanabilir.

## <a name="example"></a>Örnek

Aşağıdaki kodda `function1` ve `function2` ilk sekiz karakter aynıdır. **/Gy** ve **/H8** ile derleme bir bağlantı hatası üretir.

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
