---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2813'
title: Derleyici hatası C2813
ms.date: 11/04/2016
f1_keywords:
- C2813
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: 51de4100da8c0dd1a3b2ad1857799769b2abea24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278408"
---
# <a name="compiler-error-c2813"></a>Derleyici hatası C2813

\#/MP ile içeri aktarma desteklenmez

C2813, bir derleyici komutunda **/MP** derleyici seçeneğini ve derlemek için iki ya da daha fazla dosyayı ve bir veya daha fazla dosya [#import](../../preprocessor/hash-import-directive-cpp.md) Önişlemci yönergesini içeriyorsa yayılır. [#İmport](../../preprocessor/hash-import-directive-cpp.md) yönergesi, belirtilen tür kitaplığındaki türlerden C++ sınıfları oluşturur ve sonra bu sınıfları iki üst bilgi dosyasına yazar. Birden çok derleme birimi aynı tür kitaplığını içeri aktardığı için [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi desteklenmiyor, bu birimler aynı anda aynı üst bilgi dosyalarını yazmaya çalıştıklarında çakışırlar.

Bu derleyici hatası ve **/MP** derleyici seçeneği Visual Studio 2008 ' de yenidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2813 oluşturur. "Derle:" açıklamasında komut satırı, birden çok dosya derlemek için **/MP** ve **/c** derleyici seçeneklerini kullanmak üzere derleyiciye bildirir. Dosyalardan en az biri [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesini içerir. Bu örneği test etmek için aynı dosyayı iki kez kullanırız.

```cpp
// C2813.cpp
// compile with: /MP /c C2813.cpp C2813.cpp
#import "C:\windows\system32\stdole2.tlb"   // C2813
int main()
{
}
```
