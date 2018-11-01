---
title: Derleyici Uyarısı (düzey 1) C4743
ms.date: 11/04/2016
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: d17fd65f1108aab6e3ce97ec75c0ffb899c06cda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441853"
---
# <a name="compiler-warning-level-1-c4743"></a>Derleyici Uyarısı (düzey 1) C4743

'*türü*'başka bir boyutu vardır'*dosya1*'ve'*dosya2*': *numarası* ve *numarası* bayt

İki dosyalarında tanımlanan ya da başvurulan bir dış değişkenine bu dosyaları farklı türleri vardır ve derleyici, belirlenen değişkenin boyutu *dosya1* değişkenin boyutu farklıdır *dosya2*.

Bu uyarı için C++ yayılabilir, önemli durum yoktur. Ardından bu bildirimler sanal işlevler içeriyorsa ve bildirimleri aynı değilse, iki farklı dosyanın aynı adla aynı türlerini bildirirseniz, derleyici sanal işlev tablolar için uyarı C4744 gönderebilir. Uyarı, aynı türe yönelik iki farklı boyutta bir sanal işlev tablolar bulunur ve bağlayıcı çalıştırılabilir dosyaya birleştirmek için bunlardan birini seçmeniz gerekir çünkü oluşur.  Bu yanlış sanal işlevinin çağrılması, programınızda neden mümkündür.

Bu uyarıyı çözmek için aynı tür tanımını kullanabilir veya değişkenleri ve türleri için farklı adlar kullanın.

## <a name="example"></a>Örnek

Bu örnek, türü bir tanım içeriyor.

```
// C4743a.cpp
// compile with: /c
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

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4743 oluşturur.

```
// C4743b.cpp
// compile with: C4743a.cpp /W1 /GL /O2
// C4743 expected
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