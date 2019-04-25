---
title: volatile (C++)
ms.date: 11/04/2016
f1_keywords:
- volatile_cpp
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
ms.openlocfilehash: 73243841b2ad02bcc165b2910ac54283028e6cf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243964"
---
# <a name="volatile-c"></a>volatile (C++)

Programda bir nesnenin donanım tarafından değiştirilebileceğini bildirmek için kullanabileceğiniz bir tür niteleyicisi.

## <a name="syntax"></a>Sözdizimi

```
volatile declarator ;
```

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici bu anahtar sözcük nasıl yorumlayacağını değiştirmek için derleyici anahtarı.

Visual Studio yorumlar **geçici** hedef mimari bağlı olarak farklı anahtar sözcüğü. Hayır ise ARM için **/volatile** derleyici seçeneği belirtilmemişse, derleyici yapar gibi **/volatile:iso** belirtildi. Hayır ise ARM dışındaki mimariler için **/volatile** derleyici seçeneği belirtilmemişse, derleyici yapar gibi **/volatile:ms** belirtildi; bu nedenle, mimarileri için dışında ARM biz kesin Belirttiğiniz öneri **/volatile:iso**ve iş parçacıkları arasında paylaşılan bellek ile uğraşırken açık eşitleme bilgileri ve derleyici iç bilgileri kullanın.

Kullanabileceğiniz **geçici** kesme işleyicileri gibi zaman uyumsuz işlemler tarafından kullanılan bellek konumlarına erişim sağlamak için niteleyicisi.

Zaman **geçici** de sahip bir değişken üzerinde kullanılan [__restrict](../cpp/extension-restrict.md) anahtar sözcüğü, **geçici** önceliklidir.

Varsa bir **yapı** üye olarak işaretlenmiş **geçici**, ardından **geçici** tüm yapıya yayılır. Bir yapı kopyalanabilen bir uzunluğu geçerli mimariye bir yönerge kullanarak yoksa **geçici** o yapıda tamamen kaybolabilir.

**Geçici** anahtar sözcüğü, bir alan üzerinde hiçbir etkisi olmayabilir, aşağıdaki koşullardan biri doğru ise:

- Geçici alanın uzunluğu bir yönerge kullanarak geçerli mimariye kopyalanabilmesi için en büyük boyutu aşıyor.

- En dıştaki içeren uzunluğu **yapı**— ya da büyük olasılıkla iç içe bir üyesi ise **yapı**— bir yönerge kullanarak geçerli mimariye kopyalanabilmesi için en fazla boyutu aşıyor.

İşlemci önbelleğe alınamaz bellek erişimlerinin yeniden olsa da, önbelleğe alınamaz değişkenler olarak işaretlenmesi gerekir **geçici** sıralamaması için derleyicinin bellek yeniden değil.

Olarak bildirilen nesneler **geçici** değerlerini dilediğiniz zaman değiştirebilirsiniz çünkü belirli iyileştirmelerde kullanılmaz.  İstek geldiğinde, önceki yönerge aynı nesneden bir değer istese bile, sistem her zaman geçici bir nesnenin geçerli değerini okur.  Ayrıca, nesnenin değeri atama üzerine hemen yazılır.

## <a name="iso-compliant"></a>ISO Uyumlu

C# volatile anahtar sözcüğü ile tanıdık veya davranışını aşina olduğunuz **geçici** önceki Visual C++ sürümlerinde dikkat edin, C ++ 11 ISO standart **geçici** anahtar sözcüğü farklı ise Visual Studio'da desteklendiğine olduğunda [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği belirtildi. (ARM için bu varsayılan olarak belirtilir). **Geçici** C ++ 11 ISO standart kod sözcüktür yalnızca donanım erişimi için; kullanılacak iş parçacıkları arası iletişim için kullanmayın. İş parçacıkları arası iletişim için gibi mekanizmaları kullanın [std::atomic\<T >](../standard-library/atomic.md) gelen [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md).

## <a name="end-of-iso-compliant"></a>ISO Uyumluluğunun Sonu

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Zaman **/volatile:ms** derleyici seçeneği kullanıldığında — ARM dışındaki mimariler hedeflendiğinde varsayılandır tarafından — derleyici koruma yanı sıra geçici nesnelere başvurular arasındaki sırayı da korumak için ek bir kod oluşturur. diğer genel nesnelere başvurular için sıralama. Özellikle:

- Geçici bir nesneye yazma (geçici yazma olarak da bilinir) işleminde Sürüm semantiği vardır; yani bir yönerge dizisindeki geçici bir nesne için yazma işleminden önce olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici yazmadan önce olur.

- Geçici bir nesneyi okuma (geçici okuma olarak da bilinir) işleminde Alma semantiği vardır; yani bir yönerge dizisindeki geçici bir bellek için okuma işleminden sonra olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici okumadan önce olur.

Bu, bellek kilitleri ve çok iş parçacıklı uygulamaların sürümlerinde geçici nesnelerin kullanılabilmesini sağlar.

> [!NOTE]
>  Bağlı olduğunda ne zaman sağlanan Gelişmiş garanti **/volatile:ms** derleyici seçeneği kullanıldığında, kod taşınabilir değildir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[const ve volatile İşaretçileri](../cpp/const-and-volatile-pointers.md)