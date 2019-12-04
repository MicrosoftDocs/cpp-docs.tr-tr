---
title: Derleyici hatası C2813
ms.date: 11/04/2016
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: b36e966d897b1a3f9a4f601ef281091160da34c3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750942"
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
