---
title: Bağlayıcı araçları uyarısı LNK4224 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bdffdf3469cc3a0e5d41b0504b882513d44b63c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703993"
---
# <a name="linker-tools-warning-lnk4224"></a>Bağlayıcı Araçları Uyarısı LNK4224

> *seçenek* artık desteklenmektedir; göz ardı

## <a name="remarks"></a>Açıklamalar

Geçersiz, artık kullanılmayan bağlayıcı seçeneği belirtilen ve yoksayıldı.

Örneğin, / Comment yönergesi görünüyorsa LNK4224 ortaya çıkabilir. obj. / Comment yönergesi yoluyla eklenmiş [Açıklama (C/C++)](../../preprocessor/comment-c-cpp.md) pragma, kullanım dışı exestr seçeneğini kullanarak. DUMPBIN kullanmak [/ALL](../../build/reference/all.md) bağlayıcı yönergeleri .obj dosyasında görüntülemek için.

Mümkünse, .obj kaynağı değiştirmek ve pragma kaldırın. Bu uyarıyı yok sayarsanız bir .executable ile derlenmiş mümkündür **/CLR: pure** beklendiği gibi çalışmaz. **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

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