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
ms.openlocfilehash: 841b2e1e4ffbec87a170c45be8ad0cd0f831a0ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371908"
---
# <a name="volatile-c"></a>volatile (C++)

Programda bir nesnenin donanım tarafından değiştirilebileceğini bildirmek için kullanabileceğiniz bir tür niteleyicisi.

## <a name="syntax"></a>Sözdizimi

```
volatile declarator ;
```

## <a name="remarks"></a>Açıklamalar

Derleyicinin bu anahtar sözcüğü nasıl yorumladığını değiştirmek için [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici anahtarını kullanabilirsiniz.

Visual **Studio, hedef** mimariye bağlı olarak geçici anahtar sözcüğü farklı şekilde yorumlar. ARM için **, /volatile** derleyici seçeneği belirtilmemişse, derleyici **/volatile:iso** belirtilmiş gibi gerçekleştirir. ARM dışındaki mimariler için , **/uçucu** derleyici seçeneği belirtilmemişse, derleyici **/volatile:ms** belirtilmiş gibi gerçekleştirir; bu nedenle, ARM dışındaki mimariler **için,/volatile:iso**belirtmenizi ve iş parçacıkları arasında paylaşılan bellekle uğraşırken açık senkronizasyon ilkelleri ve derleyici içsellerini kullanmanızı şiddetle öneririz.

Kesme işleyicileri gibi eşsenkronize işlemler tarafından kullanılan bellek konumlarına erişim sağlamak için **geçici** niteleyiciyi kullanabilirsiniz.

**Uçucu** da [__restrict](../cpp/extension-restrict.md) anahtar kelime olan bir değişken üzerinde kullanıldığında, **uçucu** önceliklidir.

Bir **yapı** üyesi **uçucu**olarak işaretlenmişse, **uçucu** tüm yapıya yayılır. Bir yapının bir yönerge kullanılarak geçerli mimaride kopyalanabilecek bir uzunluğu yoksa, bu yapıda **geçici** madde tamamen kaybolabilir.

Aşağıdaki koşullardan biri **doğruysa, geçici** anahtar kelimenin bir alan üzerinde hiçbir etkisi olmayabilir:

- Geçici alanın uzunluğu bir yönerge kullanarak geçerli mimariye kopyalanabilmesi için en büyük boyutu aşıyor.

- Dıştan en dışta bulunan **yapının**uzunluğu (veya iç içe ayrılmış bir **yapının**üyesiyse) tek bir yönerge kullanılarak geçerli mimaride kopyalanabilecek maksimum boyutu aşıyor.

İşlemci önbelleğe alınamayan bellek erişimlerini yeniden sıralamasa da, derleyicinin bellek erişimlerini yeniden sipariş etmediğini garanti etmek için önbelleğe alınamayan değişkenler **geçici** olarak işaretlenmelidir.

**Geçici** olarak bildirilen nesneler, değerleri herhangi bir zamanda değişebileceğinden belirli optimizasyonlarda kullanılmaz.  İstek geldiğinde, önceki yönerge aynı nesneden bir değer istese bile, sistem her zaman geçici bir nesnenin geçerli değerini okur.  Ayrıca, nesnenin değeri atama üzerine hemen yazılır.

## <a name="iso-compliant"></a>ISO Uyumlu

C# geçici anahtar sözcüğüne aşinaysanız veya Microsoft C++ derleyicisinin (MSVC) önceki sürümlerindeki **geçici** davranışa aşinaysanız, C++11 ISO Standart **geçici** anahtar sözcüğünün farklı olduğunu ve [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği belirtildiğinde MSVC'de desteklendiğinde niçin desteklendiklerini unutmayın. (ARM için bu varsayılan olarak belirtilir). C++11 ISO Standart kodundaki **geçici** anahtar kelime yalnızca donanım erişimi için kullanılır; iş parçacığı iletişimi için kullanmayın. İş parçacıkları arası iletişim için, [C++ Standart Kitaplığı'ndan](../standard-library/cpp-standard-library-reference.md) [\<std::atomik T>](../standard-library/atomic.md) gibi mekanizmaları kullanın.

## <a name="end-of-iso-compliant"></a>ISO Uyumluluğunun Sonu

**Microsoft'a Özgü**

**/volatile:ms** derleyici sevesi kullanıldığında-varsayılan olarak ARM dışındaki mimariler hedeflendiğinde-derleyici, diğer genel nesnelere yapılan atıflara yapılan sıralamayı sürdürmenin yanı sıra geçici nesnelere yapılan atıflar arasında sıralamayı sürdürmek için ek kod oluşturur. Özellikle:

- Geçici bir nesneye yazma (geçici yazma olarak da bilinir) işleminde Sürüm semantiği vardır; yani bir yönerge dizisindeki geçici bir nesne için yazma işleminden önce olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici yazmadan önce olur.

- Geçici bir nesneyi okuma (geçici okuma olarak da bilinir) işleminde Alma semantiği vardır; yani bir yönerge dizisindeki geçici bir bellek için okuma işleminden sonra olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici okumadan önce olur.

Bu, bellek kilitleri ve çok iş parçacıklı uygulamaların sürümlerinde geçici nesnelerin kullanılabilmesini sağlar.

> [!NOTE]
> **/volatile:ms** derleyicisi seçeneği kullanıldığında sağlanan gelişmiş garantiye dayandığında, kod taşınabilir değildir.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[const ve volatile İşaretçiler](../cpp/const-and-volatile-pointers.md)
