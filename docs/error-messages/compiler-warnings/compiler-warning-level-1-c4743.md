---
title: Derleyici Uyarısı (düzey 1) C4743
ms.date: 05/13/2019
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: 53ead0e34b55eca44399cee09f1947a12e1eadd3
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611836"
---
# <a name="compiler-warning-level-1-c4743"></a>Derleyici Uyarısı (düzey 1) C4743

'*türü*'başka bir boyutu vardır'*dosya1*'ve'*dosya2*': *numarası* ve *numarası* bayt

İki dosyalarında tanımlanan ya da başvurulan bir dış değişkenine bu dosyaları farklı türleri vardır ve derleyici, belirlenen değişkenin boyutu *dosya1* değişkenin boyutu farklıdır *dosya2*.

## <a name="remarks"></a>Açıklamalar

Bu uyarı için yayılabilir, önemli bir durumda olduğundan C++. Ardından bu bildirimler sanal işlevler içeriyorsa ve bildirimleri aynı değilse, iki farklı dosyanın aynı adla aynı türlerini bildirirseniz, derleyici sanal işlev tablolar için uyarı C4744 gönderebilir. Uyarı, aynı türe yönelik iki farklı boyutlardaki sanal işlev tablolar bulunur ve bağlayıcı çalıştırılabilir dosyaya birleştirmek için bunlardan birini seçmeniz gerekir çünkü oluşur.  Bu, yanlış sanal işlevinin çağrılması, programınızda sonuçlanabilir mümkündür.

Bu uyarıyı çözmek için aynı tür tanımını kullanabilir veya değişkenleri ve türleri için farklı adlar kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4743 oluşturur. Bu derleme için hem dosyaları aynı klasöre yerleştirin ve çalıştırın  

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
