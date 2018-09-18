---
title: Bağlayıcı araçları hatası LNK1179 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d22ebb329d390d44aea44ff9dc6f3bf2f86a1d26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117464"
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