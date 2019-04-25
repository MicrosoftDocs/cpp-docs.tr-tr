---
title: Derleyici Hatası C2813
ms.date: 11/04/2016
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: 38b4bad77f836053f86a06491ef6bebbcc16671a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265990"
---
# <a name="compiler-error-c2813"></a>Derleyici Hatası C2813

\#içeri aktarma ile /MP desteklenmiyor

Bir derleyici komut belirtirseniz C2813 yayılan **/MP** derleyici seçeneği ve iki veya daha fazla dosya derleme ve bir veya daha fazla dosya içeren[#import](../../preprocessor/hash-import-directive-cpp.md) önişlemci yönergesi. [#İmport](../../preprocessor/hash-import-directive-cpp.md) yönergesi, belirtilen tür kitaplığındaki tür C++ sınıfları oluşturur ve sonra bu sınıfların iki üstbilgi dosyasına yazar. [#İmport](../../preprocessor/hash-import-directive-cpp.md) birden çok derleme biriminden aynı tür kitaplığı içeri aktarırsanız, aynı anda aynı üst bilgi dosyaları yazma çalıştıklarında bu birimleri çakıştığından yönergesi desteklenmiyor.

Bu derleyici hatası ve **/MP** derleyici seçeneğini Visual Studio 2008'de yenidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2813 oluşturur. Komut satırında "ile derleme:" açıklamanın gösterildiği kullanılacağını derleyiciye **/MP** ve **/c** birkaç dosyalarını derlemek için derleyici seçenekleri. Dosya en az birini içeren [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi. Bu örnekte test etme amacıyla iki kez aynı dosyanın kullanırız.

```
// C2813.cpp
// compile with: /MP /c C2813.cpp C2813.cpp
#import "C:\windows\system32\stdole2.tlb"   // C2813
int main()
{
}
```