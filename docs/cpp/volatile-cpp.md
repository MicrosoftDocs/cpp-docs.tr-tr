---
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
ms.openlocfilehash: 6d193c530cbe0258d8713883b769fe4828a248c1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187433"
---
# <a name="volatile-c"></a>volatile (C++)

Programda bir nesnenin donanım tarafından değiştirilebileceğini bildirmek için kullanabileceğiniz bir tür niteleyicisi.

## <a name="syntax"></a>Sözdizimi

```
volatile declarator ;
```

## <a name="remarks"></a>Açıklamalar

Derleyicinin bu anahtar sözcüğü nasıl yorumlayacağını değiştirmek için [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici anahtarını kullanabilirsiniz.

Visual Studio, hedef mimarisine bağlı olarak **geçici** anahtar sözcüğünü farklı şekilde yorumlar. ARM için, bir **/volatile** derleyici seçeneği belirtilmemişse, derleyici **/volatile: iso** belirtilmişse olarak çalışır. ARM dışındaki mimariler için, bir **/volatile** derleyici seçeneği belirtilmemişse, derleyici, **/volatile: MS** belirtilmişse olarak çalışır; Bu nedenle, ARM dışındaki mimariler **için, iş**parçacıkları arasında paylaşılan bellek ile ilgilenirken doğrudan eşitleme temelleri ve derleyici iç bilgileri kullanmanızı kesinlikle öneririz.

Kesme işleyicileri gibi zaman uyumsuz süreçler tarafından kullanılan bellek konumlarına erişim sağlamak için **geçici** niteleyiciyi kullanabilirsiniz.

Aynı zamanda [__restrict](../cpp/extension-restrict.md) anahtar sözcüğünü içeren bir değişkende **geçici** kullanıldığında, **geçici** önceliklidir.

Bir **struct** üyesi **geçici**olarak işaretlenmişse, **geçici** olarak tüm yapıya yayılır. Bir yapının bir yönerge kullanılarak geçerli mimariye kopyalanabilen bir uzunluğu yoksa, **geçici** olarak bu yapıda kaybolmuş olabilir.

Aşağıdaki koşullardan biri doğru ise, **geçici** anahtar sözcüğünün bir alanı üzerinde hiçbir etkisi olmayabilir:

- Geçici alanın uzunluğu bir yönerge kullanarak geçerli mimariye kopyalanabilmesi için en büyük boyutu aşıyor.

- En dıştaki içeren **yapının**uzunluğu — veya muhtemelen iç içe geçmiş bir **yapının**üyesiyse — bir yönerge kullanarak geçerli mimariye kopyalanabilecek maksimum boyutu aşıyor.

İşlemci, önbelleğe alınamayan bellek erişimlerini yeniden sıralayıp, derleyicinin bellek erişimlerini yeniden sıralayıp sağlamadığından emin olmak için önbelleklenebilir değişkenlerin **geçici** olarak işaretlenmesi gerekir.

Her zaman değerleri değiştirebildiğinden, **geçici** olarak belirtilen nesneler belirli iyileştirmeler içinde kullanılmaz.  İstek geldiğinde, önceki yönerge aynı nesneden bir değer istese bile, sistem her zaman geçici bir nesnenin geçerli değerini okur.  Ayrıca, nesnenin değeri atama üzerine hemen yazılır.

## <a name="iso-compliant"></a>ISO Uyumlu

C# Geçici anahtar C++ sözcük hakkında bilginiz varsa veya MICROSOFT derleyicisi 'nin (MSVC) önceki sürümlerinde **geçici** davranışı hakkında bilgi sahibiyseniz, c++ 11 ISO standart **geçici** anahtar sözcüğünün farklı olduğunu ve [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği belirtildiğinde MSVC içinde desteklendiğini unutmayın. (ARM için bu varsayılan olarak belirtilir). C++ 11 ISO standart kodundaki **volatile** anahtar sözcüğü yalnızca donanım erişimi için kullanılır; iş parçacığı içi iletişim için kullanmayın. İş parçacıkları arası iletişim için [ C++ standart kitaplıktan](../standard-library/cpp-standard-library-reference.md) [std:: atomik\<t >](../standard-library/atomic.md) gibi mekanizmalar kullanın.

## <a name="end-of-iso-compliant"></a>ISO Uyumluluğunun Sonu

**Microsoft 'a özgü**

**/Volatile: MS** derleyici seçeneği KULLANıLDıĞıNDA — ARM dışındaki mimariler hedeflenirse varsayılan olarak, derleyici diğer genel nesnelere yönelik başvurulara yönelik sıralamayı korumanın yanı sıra geçici nesnelere başvurular arasında sıralamayı sürdürmek için ek kod oluşturur. Özellikle:

- Geçici bir nesneye yazma (geçici yazma olarak da bilinir) işleminde Sürüm semantiği vardır; yani bir yönerge dizisindeki geçici bir nesne için yazma işleminden önce olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici yazmadan önce olur.

- Geçici bir nesneyi okuma (geçici okuma olarak da bilinir) işleminde Alma semantiği vardır; yani bir yönerge dizisindeki geçici bir bellek için okuma işleminden sonra olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici okumadan önce olur.

Bu, bellek kilitleri ve çok iş parçacıklı uygulamaların sürümlerinde geçici nesnelerin kullanılabilmesini sağlar.

> [!NOTE]
>  **/Volatile: MS** derleyicisi seçeneği kullanıldığında, kod, taşınabilir değil olarak sağlanmış olan gelişmiş garantisi temel alır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[const ve volatile İşaretçileri](../cpp/const-and-volatile-pointers.md)
