---
title: Derleyici Uyarısı (düzey 4) C4061
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 073e3e9cb1cb5bb6b0f66157c986072227960212
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401429"
---
# <a name="compiler-warning-level-4-c4061"></a>Derleyici Uyarısı (düzey 4) C4061

> Numaralandırıcı '*tanımlayıcı*'numaralandırıcısının switch' ın*numaralandırma*' case etiketi tarafından açıkça işlenmiyor

Belirtilen Numaralandırıcı *tanımlayıcı* ilişkili işleyici yok sahip bir `switch` olan deyimi bir `default` çalışması. Bir gözetim eksik bir durum olabilir veya bir sorun olmayabilir. Olup Numaralandırıcı varsayılan ayarda veya işlenir üzerinde bağlı olabilir. İlgili bir uyarı kullanılmayan numaralandırıcılar üzerinde `switch` yok deyimleri `default` durumda bkz [C4062](compiler-warning-level-4-c4062.md).

Varsayılan olarak bu uyarıyı kapalıdır. Varsayılan olarak kapalı olan uyarıları etkinleştirme hakkında daha fazla bilgi için bkz. [derleyici uyarıları, olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4061 oluşturur; Servis talebi eksik Numaralandırıcının düzeltmek için ekleyin:

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Uyarısı (düzey 4) C4062](compiler-warning-level-4-c4062.md)
