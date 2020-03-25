---
title: Bağlayıcı Araçları Hatası LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: a267019f1be08cc8dcffdff3b4ba0b73357cccd4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183963"
---
# <a name="linker-tools-error-lnk1179"></a>Bağlayıcı Araçları Hatası LNK1179

dosya geçersiz veya bozuk: yinelenen COMDAT ' filename '

Bir nesne modülü aynı ada sahip iki veya daha fazla Comtts içeriyor.

Bu hata, dış adların uzunluğunu sınırlayan ve [/GY](../../build/reference/gy-enable-function-level-linking.md)' nin, Comcts 'de işlev gören [/h](../../build/reference/h-restrict-length-of-external-names.md)kullanılarak kaynaklanıyor olabilir.

## <a name="example"></a>Örnek

Aşağıdaki kodda, `function1` ve `function2` ilk sekiz karakterle aynıdır. **/GY** ve **/H8** ile derleme bir bağlantı hatası oluşturur.

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
