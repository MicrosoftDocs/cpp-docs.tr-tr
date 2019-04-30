---
title: Bağlayıcı Araçları Hatası LNK2022
ms.date: 11/04/2016
f1_keywords:
- LNK2022
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
ms.openlocfilehash: e55202274c5ec3982f784ad6cdf074a5a99e922f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345329"
---
# <a name="linker-tools-error-lnk2022"></a>Bağlayıcı Araçları Hatası LNK2022

> meta veri işlemi başarısız oldu (*HRESULT*): *error_message*

Bağlayıcı, meta veriler birleştirilirken bir hata algıladı. Başarılı bir şekilde bağlamak için meta veri hataları düzeltmeniz gerekir.

Bu sorunu tanılamak için yollarından biridir çalıştırılacak **pefilename-belirteçleri** belirteçleri hangi türleri bulmak için nesne dosyaları üzerinde listelenen `error_message`ve farkları bakın.  Meta veriler, aynı ada sahip iki farklı türü geçerli değil, yalnızca LayoutType öznitelik farklı olsa bile.

Bir neden için çakışan tanımlar ancak aynı ada sahip birden çok derleme içinde bir tür (örneğin, bir yapı) mevcut olduğunda LNK2022 ve ile derleme yaparken [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  Bu durumda, türü tüm derleme özdeş bir tanımı olduğundan emin olun.  Tür adı listelenir `error_message`.

Bağlayıcı için derleyici belirtilenden farklı bir konumda bir meta veri dosyası bulduğunda, başka bir olası LNK2022 nedeni (ile [#using](../../preprocessor/hash-using-directive-cpp.md) ). Derleyiciye geçirildiğinde olduğu gibi meta veri dosyası (.dll veya .netmodule) bağlayıcıya geçirildiğinde aynı konumda olduğundan emin olun.

ATL uygulamasını, makro kullanımını oluştururken `_ATL_MIXED` en az birinde kullanılırsa, tüm derleme içinde gereklidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, boş bir türü tanımlar.

```cpp
// LNK2022_a.cpp
// compile with: /clr /c
public ref class Test {};
```

## <a name="example"></a>Örnek

Bu örnek, aynı ada ancak farklı tanımları türlerini içeren iki kaynak kodu dosyaları bağlayamazsınız gösterir.

Aşağıdaki örnek, LNK2022 oluşturur.

```cpp
// LNK2022_b.cpp
// compile with: LNK2022_a.cpp /clr /LD
// LNK2022 expected
public ref class Test {
   void func() {}
   int var;
};
```