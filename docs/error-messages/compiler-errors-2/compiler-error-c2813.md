---
title: Derleyici hatası C2813
ms.date: 11/04/2016
f1_keywords:
- C2813
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: 2cdf22d82046c66a50be0779f08e934a05555bb9
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810683"
---
# <a name="compiler-error-c2813"></a>Derleyici hatası C2813

\#içeri aktarma/MP ile desteklenmiyor

C2813, bir derleyici komutunda **/MP** derleyici seçeneğini ve derlemek için iki ya da daha fazla dosyayı ve bir veya daha fazla dosya[#import](../../preprocessor/hash-import-directive-cpp.md) Önişlemci yönergesini içeriyorsa yayılır. [#İmport](../../preprocessor/hash-import-directive-cpp.md) yönergesi, belirtilen C++ tür kitaplığındaki türlerden sınıflar oluşturur ve sonra bu sınıfları iki üst bilgi dosyasına yazar. Birden çok derleme birimi aynı tür kitaplığını içeri aktardığı için [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi desteklenmiyor, bu birimler aynı anda aynı üst bilgi dosyalarını yazmaya çalıştıklarında çakışırlar.

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
