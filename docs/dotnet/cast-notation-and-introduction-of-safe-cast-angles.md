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
ms.openlocfilehash: 6b9432b40099f9893d7fd270faf5375646fb0493
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111646"
---
# <a name="cast-notation-and-introduction-of-safecastltgt"></a>Dönüştürme gösterimi ve safe_cast giriş&lt;&gt;
Dönüştürme gösterimi C++ için Visual C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Varolan bir yapısını değiştirme ilk yapısı hazırlayın daha farklı ve daha zor bir deneyimdir. İdeal yeniden yapılandırma ve var olan yapısal bağımlılıklarla mümkün olduğunu arasında bir seçim doğru çözüm eğilimindedir ve daha az serbestlik derecesi vardır.  
  
 Dil genişletmesi başka bir örnektir. Nesne yönelimli programlamanın önemli bir standardı haline geldi gibi geri 1990 içinde bir tür kullanımı uyumlu alta c++ gerek duyuldu. Alt türe çevirme kullanıcı açık dönüştürme bir temel sınıf işaretçi veya bir işaretçi başvuru veya türetilmiş bir sınıf Başvurusu ' dir. Alt türe çevirme açık atama gerektirir. Temel sınıf işaretçisinin fiili türü bir durum çalışma zamanının olduğunu sebebi; Derleyici, bu nedenle denetlenemiyor. Veya, ifade etmek dinamik çözümleme çeşit bir sanal işlev çağrısı gibi bir alta gerektirir. Bu iki soruya yol açar:  
  
-   Neden bir alta nesne yönelimli programlamada gerekli olması gerekiyor mu? Sanal işlev mekanizması yeterli değil mi? Diğer bir deyişle, neden aşağıdakilerden herhangi bir alta (veya her tür cast) gereksinimini tasarım hatası olduğunu talep edilemiyor?  
  
-   Neden alta dönüştürme desteği C++'ta bir sorun olması gerekiyor mu? Sonuçta, nesne yönelimli dillerde Smalltalk gibi bir sorun değildir (veya daha sonra Java ve C#)? Bir alta zor destekleme yapar C++ hakkında nedir?  
  
 Bir sanal işlev türleri ailesi için ortak bir türü bağımlı algoritması temsil eder. (Biz, ISO-C++ desteklenmez, ancak CLR programlamada kullanılabilen ve ilginç tasarım alternatif temsil eden arabirimleri değerlendiriyorsanız değil). O ailenin tasarımı genellikle ortak arabirimi (sanal işlevler) ve bir dizi uygulama gerçek ailesi türlerinde temsil eden somut türetilmiş sınıfları bildirme Özet temel sınıf olan sınıf hiyerarşisi tarafından temsil edilen etki alanı.  
  
 A `Light` bir bilgisayarda oluşturulan görüntülerin (CGI) uygulama etki alanı, örneğin, hiyerarşide olacaktır ortak öznitelikleri gibi `color`, `intensity`, `position`, `on`, `off`ve benzeri. Belirli bir açık bir yenilik, tek yönlü ışığı, olmayan yönlü ışık (sun düşünün) veya belki ahır kapısı açık olup olmadığını endişelenmeden ortak arabirimi kullanarak bir birkaç ışık kontrol edebilirsiniz. Bu durumda, belirli bir açık-sanal arayüzünü denemek için tür alta gerekli değildir. Bir üretim ortamında, ancak, hız önemlidir. Biri alta olabilir ve her yöntemin sanal mekanizmayı kullanarak yerine satır içi yürütme çağrılarının gerçekleştirilebilir Böyle yaparak açıkça.  
  
 Bu nedenle, bir ihtiyacını c++ çalışma zamanı performansı önemli kazanç karşılığında sanal mekanizmayı gizlemek için nedenidir. (Bu el ile en iyi duruma getirme Otomasyon etkin bir araştırma alanı olduğuna dikkat edin. Ancak, açıkça kullanımlarını değiştirmekten çözmenize daha da zor olan `register` veya `inline` anahtar sözcüğü.)  
  
 Çok biçimlilik çift yapısını dışında ihtiyacını ikinci bir nedenle döner. Çok biçimlilik düşünmenin bir yolu formları bir edilgen ve dinamik çifti ayrılmıştır.  
  
 Çok biçimlilik dinamik kullanımlarını sanal çağırma (ve bir alta) temsil eder: bir programın yürütülmesini belirli bu örneğinde en temel sınıf işaretçisinin fiili türüne göre bir eylem gerçekleştirme.  
  
 Türetilmiş sınıf nesnesi için temel sınıf işaretçisini atama, ancak, edilgen çok biçimlilik biçimidir; çok biçimlilik aktarım mekanizması olarak kullanıyor demektir. Bu ana kullanımıdır `Object`, örneğin, ön genel CLR programlamada. Pasif olarak kullanıldığında, taşıma ve depolama için genellikle seçilen temel sınıf işaretçisinin çok soyuttur bir arabirim sunar. `Object`, kabaca beş yöntem kendi arabiriminden; Örneğin, sağlar Daha fazla belirli bir davranışı açık bir gerektirir alta. Biz bizim spotlight açısını veya düşme oranını ayarlamak istiyorsanız, örneğin, biz alta açıkça gerekir. Alt türler ailesi içindeki sanal arabirim yöntemlerine tüm olası yöntemlerin birçok alt kümesi olamaz ve bu nedenle bir alta her zaman içinde nesne yönelimli bir dil gerekecektir.  
  
 Neden bu C++ çok uzun bir eklemek sürdü güvenli olmadığını alta tesis nesne yönelimli bir dilde gerekir mi? İşaretçinin çalışma zamanı türü bilgileri kullanılabilir duruma nasıl sorunudur. Bir sanal işlev söz konusu olduğunda, çalışma zamanı bilgileri iki parça halinde derleyici tarafından ayarlandı:  
  
-   Bir ek sanal tablo işaretçi üyesi sınıf nesnesi içerir (ya da başlangıcında veya sınıf nesnesi; sonuna o kendisinin ilginç bir geçmişi vardır) uygun sanal tabloyu adresleri. Örneğin, bir spotlight nesnesi spotlight sanal bir tablo, bir tek yönlü ışık, tek yönlü ışık sanal tablosu vb. adresleri  
  
-   Tablo yuvasında sabit her sanal işlev ilişkili bir vardır ve çağrılacak gerçek örneği tablo içinde saklanan adresi tarafından temsil edilen. Örneğin, sanal `Light` yıkıcısı yuva 0 ile ilişkili `Color` ile Yuva 1 ve benzeri. Derleme zamanında ayarlama ve en az bir ek yükü temsil esnek olmayan, etkin bir strateji olmasıdır.  
  
 , Daha sonra türü bilgileri işaretçi ikinci bir adres ekleyerek veya doğrudan tür kodlama bazı sıralama ekleyerek C++ işaretçileri boyutunu değiştirmeden kullanılabilmesi nasıl sorunudur. Bu bu programcıları (ve programlar) kabul edilemez, hala baskın kullanıcı topluluğu olan nesne yönelimli kip - kullanmamaya karar verin. Çok biçimli sınıf türleri için özel bir işaretçi tanıtmak için başka bir olasılığı olan, ancak bu kafa karışıklığına neden ve özellikle işaretçi aritmetiği sorunları iki arası karışık zorlaştırır. Bu da her işaretçinin şu anda ilişkili türünü ve dinamik güncelleştirme ile ilişkilendiren bir çalışma zamanı tablo korumak için kabul edilemez.  
  
 Daha sonra farklı fakat meşru programlama istekleri olan kullanıcı toplulukları çifti sorunudur. Çözüm, her yalnızca kendi aspiration ancak çalışmanız olanağı sağlayan iki topluluk arasında bir seçim olması gerekir. Bu iki tarafında önerdiği çözüm uygulanamaz ve çözüm küçüktür kusursuz olmasını son olarak uygulanan anlamına gelir. Asıl çözümleme çok biçimli bir sınıf tanımı döner: bir çok biçimli bir sanal işlev içeren bir sınıftır. Çok biçimli bir sınıf bir dinamik tür kullanımı uyumlu alta destekler. Tüm çok biçimli sınıflar, ilişkili sanal tablosu için ek bir işaretçi üyesi içerdiğinden bu Koru-pointer-adres olarak sorununu çözer. İlişkili tür bilgisi, bu nedenle, bir genişletilmiş sanal tablo yapısında depolanabilir. Tür kullanımı uyumlu alta maliyetini (neredeyse) tesis kullanıcılarına yerelleştirilmiş.  
  
 Tür kullanımı uyumlu alta sonraki sorun sözdizimini oluştu. Bir cast olduğundan, ISO-C++ komitesi orijinal teklif sade dönüştürme sözdizimi, bu örnekte olduğu gibi kullanılır:  
  
```  
spot = ( SpotLight* ) plight;  
```  
  
 ancak kullanıcının dönüştürme maliyetini denetlemesine izin vermediğinden bu komitesi tarafından reddedildi. Dinamik tür kullanımı uyumlu alta sözdiziminde daha önce Güvensiz olarak ancak statik varsa atama gösterimi, sonra bir değiştirme haline gelir ve kullanıcı gereksiz ve belki de çok pahalı olduğunda çalışma zamanı bastırma edemez.  
  
 Genel olarak, C++'da yoktur her zaman derleyici tarafından desteklenen işlevleri gizlemek bir mekanizma. Örneğin, biz ya da sınıf kapsamı işlecini kullanarak sanal mekanizması devre dışı bırakabilir (`Box::rotate(angle)`) ya da bir sınıf nesnesi (yerine bir işaretçi veya başvuru o sınıfın) üzerinden sanal yöntemi çağırma. Bu ikinci gizleme dil tarafından gerekli değildir ancak uygulama sorun, geçici bir formun bildiriminde yapımı gizleme benzer kalitesi:  
  
```  
// compilers are free to optimize away the temporary  
X x = X::X( 10 );  
```  
  
 Böylece teklif daha fazla düşünmek için geri alındığı ve birkaç alternatif gösterimler olarak kabul ve formunu geri komitesi getirildi biri oluştu (`?type`), belirlenmemiş - diğer bir deyişle, dinamik doğasını. Bu kullanıcının iki form - statik veya dinamik - arasında geçiş yapmak için özelliği verdi ancak hiç kimse bundan memnun. Bu nedenle çizim panosuna oluştu. Şimdi üçüncü ve başarılı gösterimidir standart `dynamic_cast<type>`, hangi dört yeni stil cast gösterimler kümesine genelleştirilmiş.  
  
 ISO-C++ ' ta `dynamic_cast` döndürür `0` bir uygun olmayan işaretçi türüne uygulanacağını ve bir `std::bad_cast` başvuru türüne uygulandığında özel durum. C++ için Yönetilen Uzantılar uygulama `dynamic_cast` her zaman döndürülen bir yönetilen başvuru türüne (nedeniyle işaretçi yapısından) `0`. `__try_cast<type>` bir analog olarak türevi atma özel durumu sunulan `dynamic_cast`, onu oluşturur dışında `System::InvalidCastException` dönüştürme başarısız olursa.  
  
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
  
 Yeni sözdiziminde `__try_cast` olarak yeniden `safe_cast`. Yeni sözdiziminde aynı kod parçası şöyledir:  
  
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
  
 Yönetilen dünyada programcıları kodu doğrulanamaz yolla türleri arasında dönüştürme yeteneği sınırlayarak doğrulanabilen kod için izin vermek önemlidir. Bu yeni sözdizimi tarafından gösterilen dinamik programlama kip önemli bir yönüdür. Bu nedenle, eski türü atamalar örneklerini dahili olarak çalışma zamanı dönüştürmeleri olarak şekilde yeniden dönüştürülür, örneğin:  
  
```  
// internally recast into the   
// equivalent safe_cast expression above  
( array<ItemVerb^>^ ) verbList->ToArray( ItemVerb::typeid );   
```  
  
 Çok biçimlilik aktif ve Pasif modu sağladığından, diğer yandan, bazen yalnızca bir alt sanal olmayan API erişmek için alta dönüştürme gerçekleştirmek gereklidir. Bu durum ortaya çıkabilir, örneğin, bir sınıf üyeleri ile adresine herhangi (aktarım mekanizması olarak edilgen çok biçimlilik) hiyerarşi içinde yazın, ancak belirli programın bağlam içinde gerçek örneği bilinen istersiniz. Bu durumda, bir çalışma zamanı denetimi cast olan bir yük olabilir. Yeni sözdizimi yönetilen sistemler programlama dili hizmet vermek için ise, derleme zamanı vermeyle bazı araçlar sağlamalıdır (diğer bir deyişle, statik) alta. İşte bu nedenle uygulamanın `static_cast` gösterimi derleme zamanı alta kalmasına izin verilir:  
  
```  
// ok: cast performed at compile-time.   
// No run-time check for type correctness  
static_cast< array<ItemVerb^>^>(verbList->ToArray(ItemVerb::typeid));  
```  
  
 Yapan programcının güvence altına almak için bir yolu yoktur sorunudur `static_cast` doğru ve iyi zorlamanın diğer bir deyişle, yönetilen kod doğrulanabilir zorlamak için yolu yoktur. Bu daha Acil dinamik program kip yerel altında altında etkinleştirildiğinde, ancak statik ve çalışma zamanında cast arasında geçiş yapma olanağı programlama dili kullanıcı izin vermeyecek şekilde sistemi içindeki yeterli değil.  
  
 Bir performans yakalama ve yoktur durumu Yeni sözdiziminde, ancak. Yerel programlamada performans eski tür dönüştürme gösterimi ve yeni stil arasında fark yoktur `static_cast` gösterimi. Ancak yeni sözdiziminde eski Tarz atama gösterimi önemli ölçüde daha pahalı yeni stil kullanımını `static_cast` gösterimi. Derleyici iç aykırı bir çalışma zamanı denetimi eski Tarz gösterim kullanımını dönüştürür nedenidir. Ayrıca, de kodun yürütme profilini getiren uygulama aşağı - belki akıllıca yakalanmayan bir özel durum neden olur, ancak aynı hata başka bir özel durum, neden olmaz değiştirir çünkü `static_cast` gösterimi kullanılmış. Biri, kullanıcıların yeni stil gösterimi kullanmada prod yardımcı olacak düşünebilir. Ancak yalnızca başarısız olduğunda; Aksi takdirde, önemli ölçüde daha yavaş neden, görünür bir anlayış olmadan çalıştırmak için eski Tarz gösterimi kullanan programlar neden olacak aşağıdaki C Programcı Tuzaklar benzer:  
  
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
 [Genel dil değişiklikleri (C + +/ CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [/ CLR ile C türü atamalar (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)