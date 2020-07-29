---
title: Derleyici Uyarısı (düzey 4) C4512
ms.date: 11/04/2016
f1_keywords:
- C4512
helpviewer_keywords:
- C4512
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
ms.openlocfilehash: 068bdb2c7c87e8fe7cd3e482f53934de098a6166
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218097"
---
# <a name="compiler-warning-level-4-c4512"></a>Derleyici Uyarısı (düzey 4) C4512

' class ': atama işleci üretilemedi

Derleyici verilen sınıf için atama işleci oluşturamıyor. Atama işleci oluşturulmadı.

Türetilmiş sınıf tarafından erişilemeyen temel sınıf için atama işleci bu uyarıya neden olabilir.

Bu uyarıyı önlemek için, sınıf için Kullanıcı tanımlı bir atama işleci belirtin.

Derleyici aynı zamanda bir tane tanımlamayan bir sınıf için atama işleci işlevi de oluşturacaktır. Bu atama işleci, bir nesnenin veri üyelerinin üye tabanlı kopyasıdır. **`const`** Veri öğeleri başlatmadan sonra değiştirilemediğinden, sınıf bir **`const`** öğe içeriyorsa, varsayılan atama işleci çalışmaz. C4512 uyarısının başka bir nedeni, başvuru türündeki statik olmayan bir veri üyesinin bir bildirimidir. Amaç kopyalanabilir olmayan bir tür oluşturmak için bir varsayılan kopya Oluşturucu oluşturmayı da engellemeniz gerekir.

Kodunuzun C4512 uyarısını üç farklı şekilde çözebilirsiniz:

- Sınıf için açıkça bir atama işleci tanımlayın.

- **`const`** Sınıf içindeki veri öğesinden ref işlecini veya başvurusunu kaldırın.

- Uyarıyı bastırmak için #pragma [Uyarı](../../preprocessor/warning.md) ifadesini kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4512 oluşturur.

```cpp
// C4512.cpp
// compile with: /EHsc /W4
// processor: x86

class Base {
private:
   const int a;

public:
   Base(int val = 0) : a(val) {}
   int get_a() { return a; }
};   // C4512 warning

class Base2 {
private:
   const int a;

public:
   Base2(int val = 0) : a(val) {}
   Base2 & operator=( const Base2 & ) { return *this; }
   int get_a() { return a; }
};

// Type designer intends this to be non-copyable because it has a
// reference member
class Base3
{
private:
   char& cr;

public:
   Base3(char& r) : cr(r) {}
   // Uncomment the following line to explicitly disable copying:
   // Base3(const Base3&) = delete;
};   // C4512 warning

int main() {
   Base first;
   Base second;

   // OK
   Base2 first2;
   Base2 second2;

   char c = 'x';
   Base3 first3(c);
   Base3 second3 = first3; // C2280 if no default copy ctor
}
```
