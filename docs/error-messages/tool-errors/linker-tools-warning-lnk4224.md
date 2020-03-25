---
title: Bağlayıcı Araçları Uyarısı LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: 9e52dd533d897e729aba5f2b43ea6c019a024d43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182987"
---
# <a name="linker-tools-warning-lnk4224"></a>Bağlayıcı Araçları Uyarısı LNK4224

> *seçenek* artık desteklenmiyor; LIP

## <a name="remarks"></a>Açıklamalar

Geçersiz, Kullanımdan kaldırılmış bir bağlayıcı seçeneği belirtildi ve yoksayıldı.

Örneğin,. obj içinde bir/Comment yönergesi görünürse LNK4224 oluşabilir. /Comment yönergesi, kullanım dışı exestr seçeneği kullanılarak [yorum (C/C++)](../../preprocessor/comment-c-cpp.md) pragma aracılığıyla eklenmiş olabilir. Bir. obj dosyasındaki bağlayıcı yönergelerini görüntülemek için dumpbin [/All](../../build/reference/all.md) öğesini kullanın.

Mümkünse,. obj kaynağını değiştirin ve pragmayı kaldırın. Bu uyarıyı yoksayarsanız, **/clr: Pure** ile derlenen bir yürütülebilir dosya beklendiği gibi çalışmaz. **/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK4224 oluşturur.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```
