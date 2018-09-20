---
title: Dönüştürme gösterimi ve safe_cast giriş&lt; &gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- casting
- C-style casts and /clr, motivation for new cast notation
- safe_cast keyword [C++]
ms.assetid: 4eb1d000-3b93-4394-a37b-8b8563f8dc4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 88e8165bde08b65b4f078c4b48863c2088132fca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427873"
---
# <a name="cast-notation-and-introduction-of-safecastltgt"></a>Dönüştürme gösterimi ve safe_cast giriş&lt;&gt;

Atama gösterimi, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Varolan bir yapısını değiştirme başlangıç yapısını oluşturmak daha farklı ve daha zor bir deneyimdir. Daha az serbestlik derecesi vardır ve ideal yeniden yapılandırma ve mevcut yapısal bağımlılıklarla lisans nedir arasında bir denge doğru çözüm eğilimi gösterir.

Dil uzantısıi başka bir örnektir. Nesne programlamanın bir önemli paradigma gibi geri 1990 içinde bir tür kullanımı uyumlu alta c++ gerek duyuldu. Alta dönüştürme işlemi, bir temel sınıf işaretçisi veya başvurusu bir işaretçi veya başvuru türetilmiş bir sınıfın kullanıcı tarafından açıkça dönüştürmedir. Alta dönüştürme işlemi, bir açık tür dönüştürme gerektiriyor. Nedeni temel sınıf işaretçisi gerçek türü bir yönü çalışma zamanının olmasıdır; Derleyici, bu nedenle da denetleyemiyor. Veya bir sanal işlev çağrısı gibi bir alta şekilde ifade etmek dinamik çözümleme çeşit gerektirir. Bu iki soruyla başlatır:

- Neden bir alta dönüştürme işlemi nesne yönelimli paradigma gerekli olması gerekiyor mu? Sanal işlev mekanizması yeterli değil mi? Diğer bir deyişle, neden bir gerek bir alta dönüştürme işlemi (veya herhangi bir tür bir dönüştürme) için bir tasarım hatası olduğunu talep edilemiyor?

- Neden alta dönüştürme desteği, C++'ta bir sorun olması gerekiyor mu? Sonuçta, Smalltalk gibi dillerde nesne yönelimli bir sorun değildir (veya daha sonra Java ve C#)? Destekleyen bir alta zor hale getirir ve C++ hakkında nedir?

Bir sanal işlev ailesi türleri için ortak bir türe bağımlı algoritması temsil eder. (Biz ISO-C++'da desteklenmez, ancak CLR programlamada kullanılabilir ve ilgi çekici tasarım alternatifi temsil arabirimleri değerlendiriyorsanız değil). Tasarımını ailesinde genellikle bir soyut temel sınıf bildirme (sanal işlevler) ortak arabirim ve uygulamadaki gerçek ailesi türleri temsil eden somut türetilmiş sınıf kümesi olan bir sınıf hiyerarşisi tarafından temsil edilen etki alanı.

A `Light` bir bilgisayarda oluşturulan tanımayı (CGI) uygulama etki alanı, örneğin, bir hiyerarşide olacaktır ortak öznitelikleri gibi `color`, `intensity`, `position`, `on`, `off`ve benzeri. Bir ışık spot ışığı, bir Yönlü ışık, olmayan yönlü ışık (Güneş düşünün) veya belki de ayrıntılarını ortaya çıkarır kapısı açık olup olmadığını endişelenmenize gerek kalmadan ortak arabirimi kullanılarak birkaç ışıkları kontrol edebilirsiniz. Bu durumda, belirli bir ışık-sanal arayüzünü denemek için türe alta gerekli değildir. Bir üretim ortamında, ancak hız önemlidir. Bir alt türe çevirme olabilir ve her yöntem çağrılarının satır içi yürütme sanal mekanizmasını kullanmak yerine gerçekleştirilebilir. Eğer Böyle yaparak açıkça.

Bu nedenle, bir c++ ihtiyacını çalışma zamanı performansı önemli ölçüde kazanç tanıtmanın karşılığında sanal mekanizması bastırmak için nedenidir. (Bu el ile iyileştirme otomasyonunu etkin bir alan araştırma olduğuna dikkat edin. Ancak, açık kullanımını değiştirmekten çözmek daha da zor olan `register` veya `inline` anahtar sözcüğü.)

Alt türe çevirme için ikinci bir neden çok biçimlilik çift yapısını dışında döner. Çok biçimlilik düşünme yollarından biri formları bir pasif ve dinamik çifti ayrılmıştır.

Sanal bir çağırma (ve bir alta) dinamik kullanan çok biçimlilik türünü temsil eder: bir temel sınıf işaretçisi, belirli bir örneğine programın yürütülmesi sırasında gerçek türüne göre bir eylem işlemi uyguluyor.

İçin taban sınıfı işaretçisini bir türetilmiş sınıf nesnesinde atama, ancak bir pasif çok biçimlilik biçimindedir; Bu, çok biçimlilik aktarım mekanizması olarak kullanıyor. Ana kullanım amacı budur `Object`, örneğin, önceden genel CLR programlamada. Pasif olarak kullanıldığında, taşıma ve depolama için genellikle seçilen temel sınıf işaretçisi çok soyut bir arabirim sunar. `Object`, örneğin; arayüz üzerinden yaklaşık beş yöntemleri sağlar. daha belirli bir davranışı açık bir gerektirir alt türe çevirme. Gündem açısı veya düşme hızını ayarlamak istiyoruz, örneğin, biz alta açıkça gerekir. Sanal arabirim alt türleri ailesi içinde tüm olası yöntemlerin çoğu alt öğelerinin bir alt kümesi yöntemlerine olamaz ve bu nedenle bir alta her zaman içinde nesne yönelimli bir dildir gerekecektir.

Neden bunu C++ kadar eklemesini sürdü tesis güvenli, alt türe çevirme nesne yönelimli bir dili, gerekli? Sorun işaretçi çalışma zamanı türü bilgileri kullanılabilir duruma nasıl olmasıdır. Bir sanal işlev söz konusu olduğunda, çalışma zamanı bilgilerini iki parça halinde derleyici tarafından ayarlanan:

- Bir ek sanal tablo işaretçi üye sınıfı nesne içeren (ya da başında veya sonunda sınıf nesnesi; bu ilgi çekici bir geçmiş olması) uygun sanal tablo adresleri. Örneğin, bir spotlight nesnesi spotlight sanal bir tablo, bir Yönlü ışık bir Yönlü ışık sanal tablosu ve benzeri adresleri

- Her bir sanal işlev tablosuna yuvası sabit sahiptir ve çağırmak için gerçek örneği tablo içinde saklanan adresi tarafından temsil edilir. Örneğin, sanal `Light` yıkıcısı yuva 0 ' ile ilişkili `Color` ile Yuva 1 ve benzeri. Derleme zamanında ayarlanır ve en az bir ek yükü temsil faaliyetini, verimli bir strateji olmasıdır.

Ardından, tür bilgilerini işaretçisi ikinci bir adres ekleyerek veya doğrudan tür kodlama bazı sıralama ekleyerek C++ işaretçileri boyutunu değiştirmeden nasıl kullanılabilir kılacağınız sorundur. Bu söz konusu programcıları (ve programlara) kabul edilemez hakim kullanıcı topluluğu olan nesne yönelimli paradigma - kullanmamaya karar. Başka bir olası polimorfik sınıf türleri için özel bir işaretçi tanıtmak için olan, ancak bu kafa karıştırıcı ve özellikle işaretçi aritmetiği sorunları olan iki arası karıştırmak yapmamı zorlaştırır. Bu da her bir işaretçi türü şu anda ilişkili ve dinamik güncelleştirme ile ilişkilendiren bir çalışma zamanı tablo korumak için kabul edilemez.

Sorun farklı fakat meşru programlama istekleri olan kullanıcı toplulukları bir çift ise. Çözüm, yalnızca kendi aspiration ancak çalışma olanağı sağlayan her iki topluluk arasında bir denge olmasını sahiptir. Bu, her iki tarafında tarafından sağlanan çözümlerin uygulanamaz ve çözüm mükemmel olmayacağı için son uygulanan anlamına gelir. Gerçek çözümleme çok biçimli bir sınıf tanımı geçici bir çözüm olmasını sağlama çerçevesinde oluşturulur: çok biçimli bir sınıf içeren bir sanal işlev biridir. Çok biçimli bir sınıf, dinamik tür açısından güvenli bir alt türe çevirme destekler. Tüm çok biçimli sınıflar, ilişkili sanal tablosu için bu ek işaretçi üye içerdiğinden bu Koru-işaretçi-adres olarak sorunu çözer. İlişkili tür bilgisi, bu nedenle, bir genişletilmiş sanal tablo yapısında depolanabilir. Tür kullanımı uyumlu alt türe çevirme maliyeti (yaklaşık) tesis kullanıcıları için yerelleştirilir.

Kendi sözdizimi tür kullanımı uyumlu alt türe çevirme sonraki sorun oluştu. Bir yayın olduğundan, ISO-C++ komitesi özgün teklifine eksiz atama sözdizimi, bu örnekte olduğu gibi kullanılır:

```
spot = ( SpotLight* ) plight;
```

ancak cast'in maliyet denetlemek kullanıcı izin vermediğinden bu komitesi tarafından reddedildi. Dinamik tür kullanımı uyumlu alt türe çevirme aynı sözdizimini önceki güvenli ancak statik varsa atama gösterimi, sonra bir değiştirme olur ve kullanıcının gereksiz ve belki de çok pahalı olduğunda çalışma zamanı bastırma edemez.

Genel olarak, C++'da, her zaman bir mekanizma yoktur, derleyici tarafından desteklenen işlevleri bastırmak. Örneğin, biz ya da sınıf kapsamı işlecini kullanarak sanal mekanizmayı kapatabilirsiniz (`Box::rotate(angle)`) veya bir sınıf nesnesi (yerine bir işaretçi veya başvuru söz konusu sınıfın) üzerinden sanal yöntemi çağırarak. Bu ikinci gizleme dil tarafından gerekli değildir, ancak bir uygulama sorunu, geçici bir biçimde bir bildirim, oluşumunu gizlemeden benzer kalitesi:

```
// compilers are free to optimize away the temporary
X x = X::X( 10 );
```

Teklif daha meselesi geri alındığı ve çeşitli diğer gösterimler ve komitesi için geri getirildi bir biçiminde olan (`?type`), belirlenmemiş - diğer bir deyişle, dinamik doğasını. Bu iki formlar arasında - statik veya dinamik - yeteneğini kullanıcının verdiği ancak hiç bundan memnun. Bu nedenle çizim panosuna oluştu. Şimdi üçüncü ve başarılı gösterimidir standart `dynamic_cast<type>`, hangi dört yeni stili tür dönüştürme gösterimler kümesine genelleştirilmiş.

ISO-C++ ' ta `dynamic_cast` döndürür `0` bir uygunsuz işaretçi türüne uygulanacağını ve bir `std::bad_cast` başvuru türüne uygulandığında özel durum. C++ için Yönetilen Uzantılar uygulama `dynamic_cast` döndürülen her zaman yönetilen başvuru türüne (nedeniyle, işaretçi gösterimi) `0`. `__try_cast<type>` değişken oluşturma özel durumu bir analog olarak sunulmuştur `dynamic_cast`atar, dışında `System::InvalidCastException` dönüştürme başarısız olursa.

```
public __gc class ItemVerb;
public __gc class ItemVerbCollection {
public:
   ItemVerb *EnsureVerbArray() [] {
      return __try_cast<ItemVerb *[]>
         (verbList->ToArray(__typeof(ItemVerb *)));
   }
};
```

Yeni sözdiziminde `__try_cast` olarak dönüştürüldü `safe_cast`. Yeni sözdiziminde aynı kod parçasını şöyledir:

```
public ref class ItemVerb;
public ref class ItemVerbCollection {
public:
   array<ItemVerb^>^ EnsureVerbArray() {
      return safe_cast<array<ItemVerb^>^>
         ( verbList->ToArray( ItemVerb::typeid ));
   }
};
```

Yönetilen dünyada, programcılar kodu doğrulanamaz yollarla türleri arasında dönüştürme becerisini sınırlayarak doğrulanabilen kod için sağlamak önemlidir. Bu, yeni sözdizimi tarafından temsil edilen dinamik programlama modelini, önemli bir yönüdür. Bu nedenle, eski stil atamaları örneklerini dahili çalışma zamanı atamaları, bu nedenle yeniden dönüştürülür, örneğin:

```
// internally recast into the
// equivalent safe_cast expression above
( array<ItemVerb^>^ ) verbList->ToArray( ItemVerb::typeid );
```

Çok biçimlilik, hem etkin hem de Edilgen modu sağladığından, diğer yandan, bazen yalnızca bir alt sanal olmayan API'sine erişim elde etmek için bir alta dönüştürme işlemi gerçekleştirmek gereklidir. Bu durum ortaya çıkabilir, örneğin, bir sınıfın üyeleri ile adresine herhangi (aktarım mekanizması olarak pasif çok biçimlilik) hiyerarşisi içinde yazın, ancak belirli program bağlam içinde gerçek örneği için bilinen istersiniz. Bu durumda, bir çalışma zamanı denetimi cast'in sahip bir yük olabilir. Yönetilen sistemler programlama dili görev yapacak yeni söz dizimini ise, bir derleme zamanı zorlu bazı araçlar sağlamanız gerekir (diğer bir deyişle, statik) alt türe çevirme. İşte bu uygulamayı `static_cast` gösterimi derleme zamanı alt türe çevirme kalmasına izin verilir:

```
// ok: cast performed at compile-time.
// No run-time check for type correctness
static_cast< array<ItemVerb^>^>(verbList->ToArray(ItemVerb::typeid));
```

Bunu yapan programcının garanti etmenin bir yolu yoktur sorunudur `static_cast` doğru ve iyi niyetli; diğer bir deyişle, yönetilen kod doğrulanabilir zorlamak için hiçbir yolu yoktur. Bu yerel altında dinamik program paradigma altında daha acil bir konudur, ancak sistem statik ve çalışma zamanı tür dönüştürme arasında geçiş yapma olanağı kullanıcı izin vermeyecek şekilde dil programlama içinde yeterli değildir.

Bir performans yakalama ve yoktur durumu Yeni sözdiziminde, ancak. Yerel programlamada, eski stil atama gösterimi yeni arasındaki performans farkı yoktur `static_cast` gösterimi. Ancak yeni sözdiziminde, eski stil atama gösterimi önemli ölçüde daha yeni kullanımını daha pahalıdır `static_cast` gösterimi. Nedeni, derleyicinin dahili olarak bir özel durum bir çalışma zamanı denetimi eski stil gösterim kullanımını dönüştüren olmasıdır. Ayrıca, de kod yürütme profilini yakalanmayan bir özel durum getirme uygulamayı - belki akıllıca olur, ancak aynı hata başka bir özel durum, neden olmaz değiştirir çünkü `static_cast` gösterimi kullanılmış. Biri, kullanıcıların yeni-stili gösteriminde kullanmada prod yardımcı olacak düşünebilir. Ancak, yalnızca başarısız olduğunda; Aksi takdirde, önemli ölçüde daha yavaş görünür bir neden, anlayış olmadan çalıştırmak için eski stil gösterimi kullanan programlar açacak aşağıdaki C Programcı düşebileceğiniz tuzakları benzer:

```
// pitfall # 1:
// initialization can remove a temporary class object,
// assignment cannot
Matrix m;
m = another_matrix;

// pitfall # 2: declaration of class objects far from their use
Matrix m( 2000, 2000 ), n( 2000, 2000 );
if ( ! mumble ) return;
```

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Dil Değişiklikleri (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[/ CLR ile C türü atamalar (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)