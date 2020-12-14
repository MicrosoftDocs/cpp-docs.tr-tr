---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4743'
title: Derleyici Uyarısı (düzey 1) C4743
ms.date: 05/13/2019
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: a8c8bcd4ef0e4d7084da34e033be4194da11727f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228488"
---
# <a name="compiler-warning-level-1-c4743"></a>Derleyici Uyarısı (düzey 1) C4743

'*Type*', '*FILE1*' ve '*dosya2*' içinde farklı boyuta sahip: *sayı* ve *sayı* baytları

İki dosyada başvurulan veya tanımlanan bir dış değişken bu dosyalarda farklı türlere sahiptir ve derleyici, *FILE1* içindeki değişken boyutunun *dosya2* içindeki değişkenin boyutundan farklı olduğunu belirledi.

## <a name="remarks"></a>Açıklamalar

Bu uyarının C++ için yayınlanamadığına ilişkin önemli bir durum vardır. Aynı ada sahip aynı adı iki farklı dosyada bildirirseniz, bu bildirimler sanal işlevler içeriyorsa ve bildirimler aynı değilse, derleyici sanal işlev tabloları için uyarı C4744 ' i yayabilir. Aynı tür için iki farklı boyutlu sanal işlev tablosu olduğu ve bağlayıcı çalıştırılabilire eklemek için bunlardan birini seçmesi gerektiği için uyarı oluşur.  Programınızın yanlış sanal işlevi aramasını sağlayabilir.

Bu uyarıyı çözümlemek için aynı tür tanımını kullanın veya türler ya da değişkenler için farklı adlar kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4743 oluşturur. Derlemek için, her iki dosyayı da aynı klasöre yerleştirin ve ardından Çalıştır  

```cmd
cl /EHsc /W1 /GL /O2 C4743a.cpp C4743b.cpp
```

```cpp
// C4743a.cpp
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
};

void C::f1(void) {}
void C::f2(void) {}
void C::f3(void) {}
C q;
```

```cpp
// C4743b.cpp
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
    virtual void f4(void);
    virtual void f5(void);
};

void C::f4(void) {}
void C::f5(void) {}
C x;

int main() {}
```
