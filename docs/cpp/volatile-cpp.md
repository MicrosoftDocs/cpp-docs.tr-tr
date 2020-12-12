---
description: 'Daha fazla bilgi edinin: volatile (C++)'
title: volatile (C++)
ms.date: 05/07/2019
f1_keywords:
- volatile_cpp
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
ms.openlocfilehash: cb7bda39ded03342b03ed889125992960210b940
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213344"
---
# <a name="volatile-c"></a>volatile (C++)

Programda bir nesnenin donanım tarafından değiştirilebileceğini bildirmek için kullanabileceğiniz bir tür niteleyicisi.

## <a name="syntax"></a>Syntax

```
volatile declarator ;
```

## <a name="remarks"></a>Açıklamalar

Derleyicinin bu anahtar sözcüğü nasıl yorumlayacağını değiştirmek için [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici anahtarını kullanabilirsiniz.

Visual Studio, **`volatile`** hedef mimarisine bağlı olarak anahtar sözcüğünü farklı yorumlar. ARM için, bir **/volatile** derleyici seçeneği belirtilmemişse, derleyici **/volatile: iso** belirtilmişse olarak çalışır. ARM dışındaki mimariler için, bir **/volatile** derleyici seçeneği belirtilmemişse, derleyici, **/volatile: MS** belirtilmişse olarak çalışır; Bu nedenle, ARM dışındaki mimariler **için, iş** parçacıkları arasında paylaşılan bellek ile ilgilenirken doğrudan eşitleme temelleri ve derleyici iç bilgileri kullanmanızı kesinlikle öneririz.

**`volatile`** Kesme işleyicileri gibi zaman uyumsuz süreçler tarafından kullanılan bellek konumlarına erişim sağlamak için niteleyiciyi kullanabilirsiniz.

**`volatile`** [__Restrict](../cpp/extension-restrict.md) anahtar kelimesinin de bulunduğu bir değişkende kullanıldığında **`volatile`** öncelik kazanır.

Bir **`struct`** üye olarak işaretlenmişse **`volatile`** , **`volatile`** Tüm yapıya yayılır. Bir yapının bir yönerge kullanılarak geçerli mimariye kopyalanabilen bir uzunluğu yoksa, **`volatile`** Bu yapıda tamamen kaybolmuş olabilir.

**`volatile`** Aşağıdaki koşullardan biri doğru ise anahtar sözcüğünün bir alanı üzerinde hiçbir etkisi olmayabilir:

- Geçici alanın uzunluğu bir yönerge kullanarak geçerli mimariye kopyalanabilmesi için en büyük boyutu aşıyor.

- En dıştaki içeren uzunluk uzunluğu **`struct`** — veya büyük olasılıkla iç içe geçmiş bir üyesiyse, tek bir **`struct`** yönerge kullanılarak geçerli mimariye kopyalanabilecek maksimum boyutu aşıyor.

İşlemci, önbelleğe alınamayan bellek erişimlerini yeniden sıralamaz ve **`volatile`** derleyicinin bellek erişimlerini yeniden sıralayıp sağlamadığından emin olmak için, önbelleğe alınabilir değişkenlerin olarak işaretlenmesi gerekir.

Olarak bildirildiği nesneler, **`volatile`** değerleri herhangi bir zamanda değiştirebildiğinden belirli iyileştirmeler içinde kullanılmaz.  İstek geldiğinde, önceki yönerge aynı nesneden bir değer istese bile, sistem her zaman geçici bir nesnenin geçerli değerini okur.  Ayrıca, nesnenin değeri atama üzerine hemen yazılır.

## <a name="iso-compliant"></a>ISO Uyumlu

C# geçici anahtar sözcüğünü kullandıysanız veya **`volatile`** Microsoft C++ derleyicisi 'nın (MSVC) önceki sürümlerindeki davranışı hakkında bilgi sahibiyseniz, C++ 11 ISO standart **`volatile`** anahtar sözcüğünün farklı olduğunu ve [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği belirtildiğinde MSVC 'de desteklendiğini unutmayın. (ARM için bu varsayılan olarak belirtilir). **`volatile`** C++ 11 ISO standart kodundaki anahtar sözcüğü yalnızca donanım erişimi için kullanılır; bunu iş parçacıkları arası iletişim için kullanmayın. İş parçacıkları arası iletişim için, [C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)'ndan [std:: atomik \<T> ](../standard-library/atomic.md) gibi mekanizmalar kullanın.

## <a name="end-of-iso-compliant"></a>ISO Uyumluluğunun Sonu

**Microsoft'a Özgü**

**/Volatile: MS** derleyici seçeneği KULLANıLDıĞıNDA — ARM dışındaki mimariler hedeflenirse varsayılan olarak, derleyici diğer genel nesnelere yönelik başvurulara yönelik sıralamayı korumanın yanı sıra geçici nesnelere başvurular arasında sıralamayı sürdürmek için ek kod oluşturur. Özellikle:

- Geçici bir nesneye yazma (geçici yazma olarak da bilinir) işleminde Sürüm semantiği vardır; yani bir yönerge dizisindeki geçici bir nesne için yazma işleminden önce olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici yazmadan önce olur.

- Geçici bir nesneyi okuma (geçici okuma olarak da bilinir) işleminde Alma semantiği vardır; yani bir yönerge dizisindeki geçici bir bellek için okuma işleminden sonra olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici okumadan önce olur.

Bu, bellek kilitleri ve çok iş parçacıklı uygulamaların sürümlerinde geçici nesnelerin kullanılabilmesini sağlar.

> [!NOTE]
> **/Volatile: MS** derleyicisi seçeneği kullanıldığında, kod, taşınabilir değil olarak sağlanmış olan gelişmiş garantisi temel alır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[const ve volatile Işaretçileri](../cpp/const-and-volatile-pointers.md)
