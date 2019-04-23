---
title: Derleyici Uyarısı (düzey 4) C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: 79658afc31565b708cdbd8a88f49b887cdd10cf3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59237191"
---
# <a name="compiler-warning-level-4-c4062"></a>Derleyici Uyarısı (düzey 4) C4062

> Numaralandırıcı '*tanımlayıcı*'numaralandırıcısının switch' ın*numaralandırma*' işlenmezse

Numaralandırıcı *tanımlayıcı* yok ilişkili `case` işleyicisinde bir `switch` deyimi ve hiçbir `default` yakalamak etiket. Eksik servis talebi bir gözetim olabilir ve kodunuzdaki olası bir hatadır. İlgili bir uyarı kullanılmayan numaralandırıcılar üzerinde `switch` sahip deyimleri bir `default` durumda bkz [C4061](compiler-warning-level-4-c4061.md).

Varsayılan olarak bu uyarıyı kapalıdır. Varsayılan olarak kapalı olan uyarıları etkinleştirme hakkında daha fazla bilgi için bkz. [derleyici uyarıları, olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4062 oluşturur ve bu sorunun nasıl gösterir:

```cpp
// C4062.cpp
// compile with: /EHsc /W4
#pragma warning(default : 4062)
enum E { a, b, c };
void func ( E e ) {
   switch(e) {
      case a:
      case b:
   // case c:  // to fix, uncomment this line
      break;   // no default label
   }   // C4062, enumerator 'c' not handled
}

int main() {
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Uyarısı (düzey 4) C4061](compiler-warning-level-4-c4061.md)
