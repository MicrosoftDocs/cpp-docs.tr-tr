---
title: Bağlayıcı Araçları Hatası LNK2022
ms.date: 11/04/2016
f1_keywords:
- LNK2022
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
ms.openlocfilehash: 187a63cb4bd22fc5e0d35523d97f438ba56b8576
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686364"
---
# <a name="linker-tools-error-lnk2022"></a>Bağlayıcı Araçları Hatası LNK2022

> meta veri işlemi başarısız oldu (*HRESULT*): *error_message*

Bağlayıcı meta verileri birleştirirken bir hata algıladı. Meta veri hataları başarıyla bağlanacak şekilde çözümlenmelidir.

Bu sorunu tanılamaya yönelik bir yol, içinde hangi türlerin listelenen belirteçleri bulmak için nesne dosyalarında **ıldadsm belirteçlerini** çalıştırmak `error_message` ve farklılıkları aramak için kullanılır.  Meta verilerde, yalnızca LayoutType özniteliği farklı olsa da, aynı ada sahip iki farklı tür geçerli değildir.

Bir tür (struct gibi) aynı ada sahip birden çok derleme içinde bulunması, ancak çakışan tanımlarla ve [/clr](../../build/reference/clr-common-language-runtime-compilation.md)ile DERLERKEN, LNK2022 için bir neden olur.  Bu durumda, türün tüm uygulamalarda aynı tanıma sahip olduğundan emin olun.  Tür adı ' de listelenir `error_message` .

LNK2022 'in bir diğer olası nedeni, bağlayıcının derleyiciye belirtilenden farklı bir konumda meta veri dosyası bulmasında ( [#using](../../preprocessor/hash-using-directive-cpp.md) ile). Meta veri dosyasının (. dll veya. netmodule), derleyiciye geçirildiği sırada olduğu gibi bağlayıcının aynı konumda olduğundan emin olun.

Bir ATL uygulaması oluştururken, `_ATL_MIXED` en az bir üzerinde kullanılıyorsa makronun kullanımı tüm uygulamalarda gereklidir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek boş bir tür tanımlar.

```cpp
// LNK2022_a.cpp
// compile with: /clr /c
public ref class Test {};
```

Bu örnek, aynı ada sahip ancak farklı tanımlardan oluşan türleri içeren iki kaynak kodu dosyasını bağlayamazsınız.

Aşağıdaki örnek LNK2022 oluşturur.

```cpp
// LNK2022_b.cpp
// compile with: LNK2022_a.cpp /clr /LD
// LNK2022 expected
public ref class Test {
   void func() {}
   int var;
};
```
