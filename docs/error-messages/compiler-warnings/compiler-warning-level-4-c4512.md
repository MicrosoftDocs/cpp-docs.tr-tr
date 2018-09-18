---
title: Derleyici Uyarısı (düzey 4) C4512 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4512
dev_langs:
- C++
helpviewer_keywords:
- C4512
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9aee9e7f48430ddc9b2b9a6a7f055ac8b1e32b71
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029955"
---
# <a name="compiler-warning-level-4-c4512"></a>Derleyici Uyarısı (düzey 4) C4512

'class': atama işleci üretilemedi

Derleyici, belirli bir sınıf için bir atama işleci oluşturulamıyor. Hiçbir atama işleci oluşturuldu.

Türetilmiş sınıf tarafından erişilebilir değil temel sınıf için bir atama işleci, bu uyarıyı neden olabilir.

Bu uyarıyı engellemek için sınıf için bir kullanıcı tanımlı atama işleci belirtin.

Derleyici ayrıca bir tanımlamıyor bir sınıf için bir atama işleci işlevi oluşturur. Bu atama işleci bir nesnenin veri üyelerinin kopyalamadır. Çünkü `const` veri öğeleri sınıf içeriyorsa, başlatmadan sonra değiştirilemez bir `const` öğesini varsayılan atama işleci çalışmamasına. Başka bir nedeni de C4512 uyarı bir başvuru türü statik olmayan veri üyesi bildirimidir. Amaç, kopyalanamaz türü oluşturmak için ise, varsayılan bir kopya Oluşturucu oluşturulmasını de engellemelisiniz.

C4512 uyarı kodu üç yoldan biriyle çözümleyebilirsiniz:

- Sınıfı için bir atama işleci açıkça tanımlayın.

- Kaldırma **const** veya başvuru işleci sınıftaki veri öğesi.

- #Pragma kullanın [uyarı](../../preprocessor/warning.md) uyarının gösterilmemesi için deyimi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4512 oluşturur.

```
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