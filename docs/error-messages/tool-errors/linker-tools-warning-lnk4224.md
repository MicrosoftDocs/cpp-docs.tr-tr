---
title: Bağlayıcı Araçları Uyarısı LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: eb0a019cc80e5218a52697b8bcd5e91b811d04d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160399"
---
# <a name="linker-tools-warning-lnk4224"></a>Bağlayıcı Araçları Uyarısı LNK4224

> *seçenek* artık desteklenmiyor; yoksayıldı

## <a name="remarks"></a>Açıklamalar

Bir geçersiz, eski bağlayıcı seçeneği belirtilen ve yoksayıldı.

Örneğin, / Comment yönergesi görünürse LNK4224 ortaya çıkabilir. obj. / Comment yönergesi aracılığıyla eklenebilecek [yorum (C/C++)](../../preprocessor/comment-c-cpp.md) pragması, kullanım dışı exestr seçeneğini kullanma. DUMPBIN kullanma [/ALL](../../build/reference/all.md) bir .obj dosyasında bağlayıcı yönergeleri görüntülemek için.

Mümkünse, .obj kaynağını değiştirebilir ve pragma kaldırın. Bu uyarıyı yoksayın, olası bir .executable ile derlenmiş **/CLR: pure** beklendiği gibi çalışmaz. **/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK4224 oluşturur.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```