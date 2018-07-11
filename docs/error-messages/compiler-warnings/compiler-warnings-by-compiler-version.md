---
title: Derleyici sürümüne göre derleyici uyarıları | Microsoft Docs
ms.custom: ''
ms.date: 07/03/2018
ms.technology:
- devlang-cpp
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- warnings, by compiler version
- cl.exe compiler, setting warning options
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eb91708545d2303304177093e79ea49e8fa9208
ms.sourcegitcommit: 894b3b3a91fcd8894b582747b03135c0be450c1f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37850426"
---
# <a name="compiler-warnings-by-compiler-version"></a>Derleyici sürümüne göre derleyici uyarıları

Derleyici bir sürümünü kullanarak belirttiğiniz sonra sunulan uyarıları gözardı edebileceğini [/Wv](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği. Bu, yeni bir araç takımının sürüm tanıtır ve geçici olarak yeni uyarıları bastırmak istediğiniz yapı işleminizin yönetimi için avantajlıdır. Bu seçenek, yeni hata iletileri engellemez. Tüm yeni uyarıları bastır önermiyoruz kalıcı olarak! En yüksek normal uyarı düzeyinde, her zaman derle öneririz __/W4__, kaldırıp __/Wv__ olabildiğince çabuk derleme seçeneği.

Derleyicisinin bu sürümü, yeni uyarılar eklendi:

| Ürün | Derleyicinin sürüm numarası |
|-|-|
| Visual C++ 2002 | 13.00.9466 |
| Visual C++ 2003 | 13.10.3077 |
| Visual C++ 2005 | 14.00.50727.762 |
| Visual C++ 2008 | 15.00.21022.08 |
| Visual C++ 2010 | 16.00.40219.01 |
| Visual C++ 2012 | 17.00.51106.1 |
| Visual C++ 2013 | 18.00.21005.1 |
| Visual C++ 2015 RTM | 19.00.23026.0 |
| Visual C++ 2015 güncelleştirme 1 | 19.00.23506.0 |
| Visual C++ 2015 güncelleştirme 2 | 19.00.23918.0 |
| Visual C++ 2015 güncelleştirme 3 | 19.00.24215.1 |
| Visual C++ 2017 RTM | 19.10.25017.0 |
| Visual C++ 2017 sürüm 15.3 | 19.11.25506.0 |
| Visual C++ 2017 sürüm 15.5 | 19.12.25830.0 |
| Visual C++ 2017 sürüm 15.6 | 19.13.26128.0 |
| Visual C++ 2017 sürüm 15.7 | 19.14.26428.0 |

Yalnızca birincil numara, büyük ve küçük sayılar veya ana, alt, belirtin ve yapı numaralarına __/Wv__ seçeneği. Derleyici, belirtilen sayı ile başlayan sürümleri eşleşen tüm uyarıları raporlar ve belirtilen sayıdan büyük sürümlerine yönelik tüm uyarıları bastırır. Örneğin, __/Wv:17__ içinde veya herhangi bir Visual Studio 2012 sürümünü tüm uyarıları raporları ve Visual Studio 2013 (sürüm 18) veya üzeri tüm derleyici tarafından kullanıma sunulan tüm uyarıları bastırır. Bastırmak için Visual Studio 2015'te xx.yy.zzzz güncelleştirme 2 ve daha sonra kullanabileceğiniz __/Wv:19.00.23506__. Kullanım __/Wv:19.11__ tüm uyarıları herhangi bir sürümü Visual Studio'yu daha önce Visual Studio 2017 sürüm 15.5 sürümünde, ancak Visual Studio 2017 sürüm 15.5 ve üzeri uyarıları bastırır bildirmek için.

Aşağıdaki bölümlerde her kullanarak bastırma Visual C++ sürümü xx.yy.zzzz listesinde __/Wv__ derleyici seçeneği. __/Wv__ seçeneği, belirtilen derleyici sürümleri geçerler listelenmez, uyarıları bastır olamaz.

## <a name="warnings-introduced-in-visual-c-2017-version-157-compiler-version-1914264280"></a>Visual C++ 2017 sürüm 15.7 (Derleyici sürümü 19.14.26428.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.13__.

|||
|-|-|
C4642|'*sorunu*': genel parametresi için kısıtlamalar içeri aktarılamadı '*parametre*'
C5045|Derleyici/qspectre anahtarı Bellek Yükü belirtilen için Spectre risk azaltma ekler

## <a name="warnings-introduced-in-visual-c-2017-version-156-compiler-version-1913261280"></a>Visual C++ 2017 sürüm 15.6 (Derleyici sürümü 19.13.26128.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.12__.

|||
|-|-|
C5044|Komut satırı seçeneği bir bağımsız değişken *seçeneği* yolunu işaret '*yolu*' mevcut olmayan

## <a name="warnings-introduced-in-visual-c-2017-version-155-compiler-version-1912258300"></a>Visual C++ 2017 sürüm 15.5 (Derleyici sürümü 19.12.25830.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.11__.

|||
|-|-|
C4843|'*type1*': dizi veya işlev türüne yapılan başvurunun özel durum işleyicisi erişilemiyor, kullanın '*type2*' yerine
C4844|' export module *module_name*;' artık bir modül arabirimi bildirmek için tercih edilen sözdizimi şöyledir
C5039|'*işlevi*': - EHc altında extern C işlevine işaretçi veya başvuru için büyük olasılıkla işlev özel durum atma geçirildi. Bu işlev bir özel durum oluşturursa tanımsız davranış ortaya çıkabilir.
C5040|dinamik özel durum belirtimleri yalnızca C ++ 14 ve daha önceki sürümlerde geçerlidir; noexcept(FALSE) değerlendirme
C5041|'*tanımı*': constexpr statik veri üyesi için satır dışı tanımı gerekli değildir ve C ++ 17'de kullanım dışıdır
C5042|'*bildirimi*': blok kapsamındaki işlev bildirimleri, standart C++'da belirtilen 'inline' olamaz; 'inline' tanımlayıcısını kaldırın
C5043|'*belirtimi*': özel durum belirtimi, önceki bildirimle eşleşmiyor

## <a name="warnings-introduced-in-visual-c-2017-version-153-compiler-version-1911255060"></a>Visual C++ 2017 sürüm 15.3 (Derleyici sürümü 19.11.25506.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.10__.

|||
|-|-|
C4597|Tanımsız davranış: *açıklaması*
C4604|'*türü*': yerel ve yönetilen sınırda değere göre bağımsız değişken geçirme, geçerli bir kopya Oluşturucusu gerektirir. Aksi takdirde çalışma zamanı davranışı tanımsızdır
C4749|koşullu olarak desteklenir: *açıklaması*
C4768|bağlantı belirtiminden önceki __declspec öznitelikleri yoksayılır
C4834|'nodiscard' özniteliği ile işlevin dönüş değeri atılıyor
C4841|Standart olmayan uzantı kullanıldı: *uzantısı*
C4842|birden fazla devralma kullanılarak bir türe uygulanan'offsetof ' sonucunun derleyici yayınları arasında tutarlı olması garanti edilmez
C4869|'nodiscard' yalnızca sınıflar, numaralandırmalar ve işlevleri ile void olmayan dönüş türü için uygulanabilir
C5033|'*depolama sınıfı*' artık desteklenen bir depolama sınıfı değil
C5034|İç Kullan '*iç*' neden işlevi *işlevi* Konuk kodu olarak derlenmesine neden
C5035|özelliğini '*özellik*' neden işlevi *işlevi* Konuk kodu olarak derlenmesine neden
C5036|VarArgs işlev işaretçisi dönüştürme x86arm64 ile derleme yapılırken '*type1*'to'*type2*'
C5037|'*üye işlevi*': bir sınıf şablonunun üyesi bir satır dışı tanımı varsayılan bağımsız değişkenlere sahip olamaz
C5038|veri üyesi '*Üye1*'veri üyesi sonra başlatılacak'*üye2*'

## <a name="warnings-introduced-in-visual-c-2017-rtm-compiler-version-1910250170"></a>Visual C++ 2017 RTM'de (Derleyici sürümü 19.10.25017.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.00__.

|||
|-|-|
C4468|'fallthrough': özniteliği bir case etiketi veya varsayılan etiket gelmelidir
C4698|'*özellik*' yalnızca değerlendirme amaçlıdır ve değişikliğe tabidir veya gelecekte kaldırılması güncelleştirir.
C4839|sınıfının standart dışı kullanımı*sınıfı*' bir bağımsız değişken içeren işlev bağımsız değişkeni olarak
C4840|sınıfının taşınabilir olmayan kullanımı*sınıfı*' bir bağımsız değişken içeren işlev bağımsız değişkeni olarak

## <a name="warnings-introduced-in-visual-c-2015-update-3-compiler-version-1900242151"></a>Visual C++ 2015 güncelleştirme 3'te (Derleyici sürümü 19.00.24215.1) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.00.23918__.

|||
|-|-|
C4467|ATL öznitelikleri kullanım dışı bırakılmıştır
C4596|'*adı*': üye bildiriminde geçersiz nitelenmiş ad
C4598|' #include \< *üstbilgi*\>': üst bilgisi numarası *numarası* içinde *kaynak* eşleşmiyor *kaynak* hiç konumu
C4599|'*bağımsız değişken*': *kaynak* bağımsız değişken numarası *numarası* eşleşmiyor *kaynak*

## <a name="warnings-introduced-in-visual-c-2015-update-2-compiler-version-1900239180"></a>Visual C++ 2015 güncelleştirme 2'de (Derleyici sürümü 19.00.23918.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.00.23506__.

|||
|-|-|
C4466|Eş yordam yığın eleme gerçekleştirilemedi
C4595|'*sınıfı*': üye olmayan operator new veya delete işlevleri bildirilemez satır içi
C4828|Dosyayı 0 uzaklıkta başlayan belirli bir karakter içeren x*değer* geçerli kaynak karakter kümesinde geçersiz olan (kod sayfası *numarası*).
C4868|Küme ayracıyla belirtilen Başlatıcı listesinde soldan sağa Değerlendirme sırasını derleyici zorla

## <a name="warnings-introduced-in-visual-c-2015-update-1-compiler-version-1900235060"></a>Visual C++ 2015 güncelleştirme 1 ' (Derleyici sürümü 19.00.23506.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:19.00.23026__.

|||
|-|-|
C4426|iyileştirme bayrakları üst bilgi eklendikten sonra değişti, nedeni #pragma optimize() olabilir
C4654|Önce yerleştirilmiş kod içeren önceden derlenmiş üst bilgi satırı yok sayılacak. Kodu önceden derlenmiş üst bilgiye ekleyin.
C5031|#pragma warning(pop): olası uyuşmazlık, farklı bir dosyada atılan uyarı durumu geri çağrılıyor
C5032|hiçbir karşılık gelen #pragma warning(pop) olmayan #pragma algılandı

## <a name="warnings-introduced-in-visual-c-2015-rtm-compiler-version-1900230260"></a>Visual C++ 2015 RTM'de (Derleyici sürümü 19.00.23026.0) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:18__.

|||
|-|-|
C4427|'*hata*': sabit bölümde, tanımsız davranış taşma
C4438|'*türü*': güvenli olarak çağrılamaz / await: clrcompat modunda. Varsa '*türü*' CLR çağrılar, CLR kafa Bozulması neden olabilir
C4455|' operator *adı*': bir alt çizgiyle başlamayan sabit değerli ek tanımlayıcıları ayrıldı
C4456|bildirimi '*adı*' önceki yerel bildirimi gizliyor
C4457|bildirimi '*adı*' işlev parametresini gizliyor
C4458|bildirimi '*adı*' sınıf üyesini gizliyor
C4459|bildirimi '*adı*' genel bildirimi gizliyor
C4462|'*türü*': türün GUID'i belirlenemiyor. Program çalışma zamanında başarısız olabilir.
C4463|taşma; atama *değer* değerlerinden yalnızca içerebileceği bit alanına *değer* için *değeri*
C4473|'*işlevi*': biçim dizesi için yeterli bağımsız değişken geçirildi
C4474|'*işlevi*': biçim dizesi için çok fazla bağımsız değişken geçirildi
C4475|'*işlevi*': uzunluk değiştiricisi '*değiştiricisi*'tür alanı karakteri ile kullanılamaz'*karakter*' biçim tanımlayıcıda
C4476|'*işlevi*': bilinmeyen tür alanı karakteri '*karakter*' biçim tanımlayıcıda
C4477|'*işlevi*': biçim dizesi '*dize*'türünde bir bağımsız değişken gerektirir'*türü*', ancak değişen sayıda bağımsız değişkeni *numarası* türüne sahip '*türü*'
C4478|'*işlevi*': konumsal ve konumsal olmayan yer tutucular aynı Biçim dizesinde karıştırılamaz
C4494|'*türü*': __declspec(allocator) işlev dönüş çünkü tür yoksayılıyor değil bir işaretçi veya başvuru
C4495|Standart olmayan uzantı '__super' kullanıldı: açık taban sınıfı adıyla değiştirin
C4496|kullanılan standart olmayan uzantı 'for each' kullanıldı: ranged-for deyimiyle değiştirin
C4497|Standart olmayan uzantı 'sealed' kullanıldı: 'final' ile değiştirin
C4498|Standart olmayan uzantı kullanıldı: '*uzantısı*'
C4499|'*özelleştirmesi*': bir açık özelleştirmenin (yoksayılan) depolama sınıfı olamaz
C4576|bir başlatıcı listesi tarafından izlenen parantez içine alınmış türü bir standart olmayan açık tür dönüştürme söz dizimidir
C4577|'noexcept' hiçbir özel durum işleme modu belirtilmeden kullanılan; özel durum sonlandırma garanti edilmez. / Ehsc belirtin
C4578|'abs': dönüştürme '*türü*'to'*türü*', olası veri kaybı (çağrı yapmak mı istediniz '*adı*' veya #include \<cmath >?)
C4582|'*türü*': Oluşturucu örtük olarak çağırılmamış
C4583|'*türü*': yıkıcı örtük olarak çağırılmamış
C4587|'*türü*': davranış değişikliği: Oluşturucu artık örtük olarak çağırılamaz
C4588|'*türü*': davranış değişikliği: yıkıcı artık örtük olarak çağırılamaz
C4589|Soyut sınıfı oluşturucusu*türü*'yoksayar sanal temel sınıf için Başlatıcı'*türü*'
C4591|'constexpr' çağrı derinliği sınırı *numarası* aşıldı (/ Depth\<NUMBER >)
C4592|'*türü*': sembol dinamik olarak olacaktır (uygulama sınırlandırma) başlatıldı
C4593|'*türü*': 'constexpr' çağrı değerlendirmesi adım sınırı *değer* aştı; Steps kullanın\<numarası > için belirlenen sınırı yükseltmek için
C4647|davranış değişikliği: __is_pod (*türü*) önceki sürümlerde farklı değere sahip
C4648|'carries_dependency' standart özniteliği yoksayılıyor
C4649|öznitelikler bu bağlamda göz ardı edilir
C4753|İşaretçinin sınırları bulunamıyor; MPX iç işlevi yoksayıldı
C4771|Sınırlar basit bir işaretçi kullanılarak oluşturulmalıdır; MPX iç işlevi yoksayıldı
C4774|'*açıklama*': biçim dizesi bağımsız değişkeninde beklenen *numarası* bir dize sabit değeri değil
C4775|Biçim dizesinde kullanılan standart olmayan uzantı '*dize*'işlevinin'*işlevi*'
C4776|' %*karakter*'işlevinin Biçim dizesinde izin verilmez'*işlevi*'
C4777|'*açıklama*': biçim dizesi '*dize*'türünde bir bağımsız değişken gerektirir'*türü*', ancak değişen sayıda bağımsız değişkeni *numarası* türüne sahip '*türü*'
C4778|'*açıklama*': Sonlandırılmamış biçim dizesi '*dize*'
C4838|dönüştürme işlemi '*türü*'to'*türü*' bir daraltma dönüşümü gerektirir
C5022|'*türü*': belirtilen birden fazla taşıma oluşturucuları
C5023|'*türü*': belirtilen birden fazla taşıma atama işleçleri
C5024|'*bildirimi*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı
C5025|'*bildirimi*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı
C5026|'*türü*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı
C5027|'*türü*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı
C5028|'*adı*': hizalama önceki bildirimde belirtilen (*numarası*) belirtilmemiş
C5029|Standart olmayan uzantı kullanıldı: C++ hizalama öznitelikleri değişkenlere, veri üyelerine ve etiket türlerine uygulanır
C5030|öznitelik '*özniteliği*' tanınmıyor

## <a name="warnings-introduced-in-visual-c-2013-compiler-version-1800210051"></a>Visual C++ 2013 (Derleyici sürümü 18.00.21005.1) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:17__.

|||
|-|-|
C4301|'*türü*': geçersiz kılan sanal işlev'ı yalnızca farklıdır '*bildirimi*' const/volatile niteleyicisi tarafından
C4316|'*türü*': yığın üzerinde ayrılan nesne değil hizalanmayacak *numarası*
C4380|'*türü*': varsayılan oluşturucu kullanım dışı olamaz
C4388|'*belirteci*': imzalı/imzasız uyuşmazlığı
C4423|'std::bad_alloc': sınıf tarafından yakalandı ('*türü*') satırındaki *numarası*
C4424|için catch '*türü*'öncesinde'*türü*' satırındaki *numarası*; beklenmeyen davranış 'std::bad_alloc' oluşursa neden olabilir
C4425|SAL ek açıklaması uygulanamaz '...' için
C4464|göreli ekleme yolu içeren '..'
C4575|'__vectorcall' ile uyumsuz ' / clr' seçeneği: '__stdcall' için dönüştürme
C4609|'*türü*'varsayılan arabiriminden türetilen'*türü*'type' on*türü*'. İçin varsayılan farklı bir arayüz kullanın '*türü*', veya taban/türetilmiş ilişkisini kesin.
C4754|Konumundaki karşılaştırma içindeki aritmetik işlemler için dönüştürme kuralları *açıklama*(*numarası*), bir dalın yürütülemeyeceği anlamına gelir. Cast '*türü*'to'*türü*' (veya benzer bir tür *numarası* bayt).
C4755|Konumundaki karşılaştırma içindeki aritmetik işlemler için dönüştürme kuralları *açıklama*(*numarası*), bir dalın satır içine alınmış bir işlevde yürütülemeyeceği anlamına gelir. Cast '*türü*'to'*türü*' (veya benzer bir tür *numarası* bayt).
C4767|Bölüm adı '*adı*' 8 karakterden daha uzun ve bağlayıcı tarafından kesilecek
C4770|enum'kısmen doğrulanmış '*adı*' dizin olarak kullanılıyor
C4827|0 paramterleri bir genel 'ToString' yöntemi sanal olarak işaretlenmesi gerekir ve geçersiz kılma
C4882|non-const çağrı işleçleri olan functorları concurrency::parallel_for_each içine geçirmek kullanım dışıdır
C4973|'*türü*': kullanım dışı olarak işaretlendi
C4974|'*türü*': kullanım dışı olarak işaretlendi
C4981|Warbird: işlev '*bildirimi*' __forceinline olarak değil, özel durum anlamsalları içerdiği için satır içine alınmış işaretlenmiş.
C4990|Warbird: *iletisi*
C4991|Warbird: işlev '*bildirimi*' alınanın koruma düzeyi üst büyük olduğundan __forceinline olarak satır içine alınmış işaretlenen
C4992|Warbird: işlev '*bildirimi*' Korunamayan satır içi bütünleştirilmiş içerdiğinden __forceinline olarak satır içine alınmış işaretlenen

## <a name="warnings-introduced-in-visual-c-2012-compiler-version-1700511061"></a>Visual C++ 2012 (Derleyici sürümü 17.00.51106.1) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:16__.

|||
|-|-|
C4330|öznitelik '*özniteliği*'için bölüm'*bölüm*' yoksayıldı
C4415|Yinelenen __declspec (code_seg ('*adı*'))
C4416|__declspec(code_seg(...)) boş dize içeriyor: yoksayıldı
C4417|bir açık şablon örneği oluşturma işlevinde __declspec(code_seg(...)) bulunamaz: yoksayıldı
C4418|bir üzerindeki __declspec(code_seg(...)) yoksayıldı
C4419|'*adı*'özel başvuru sınıfına uygulandığında etkisizdir'*türü*'.
C4435|'*türü*': / vd2 altındaki Nesne düzeni sanal tabanı nedeniyle değişecek '*türü*'
C4436|dynamic_cast'sanal tabanından '*türü*'to'*türü*' oluşturucu veya yıkıcı içinde oluşturulmuş bir nesne ile başarısız olabilir
C4437|dynamic_cast'sanal tabanından '*türü*'to'*türü*' bazı bağlamlarda başarısız olabilirdi
C4443|Beklenen pragma parametresinin '0', '1' veya '2'
C4446|'*türü*': üye eşlenemez '*adı*' içinde bu tür, tür adı çakışması nedeniyle. Yöntem adlandırıldı '*adı*'
C4447|bulunan iş parçacığı modeli olmadan 'main' imzası. Kullanmayı ' int main (Platform::Array\<Platform::String ^ > ^ args)'.
C4448|'*türü*' meta verilerinde belirtilmiş bir varsayılan arabirim yok. Gerçekleştiriliyor: '*türü*', hangi çalışma zamanında başarısız olabilir.
C4449|'*türü*' bir tür '[WebHostHidden]' olarak işaretlenmelidir
C4450|'*türü*'öğesinden türetildiği için '[WebHostHidden]' olarak işaretlenmelidir'*türü*'
C4451|'*türü*': başvuru sınıfının kullanımı*türü*' Bu bağlamda geçersiz nesne bağlamlarında hazırlama açabilir iç
C4452|'*türü*': Ortak tür genel kapsamda olamaz. Bu, çıkış .winmd dosyasının adının bir alt ad alanında olmalıdır.
C4453|'*türü*': '[WebHostHidden]' türü olmayan genel bir türün yayımlanmış yüzeyinde kullanılmamalıdır '[WebHostHidden]'
C4454|'*türü*' [DefaultOverload] belirtilen zorunda kalmadan aşırı giriş parametrelerinin sayısından fazla. Çekme '*bildirimi*' olarak varsayılan aşırı yükleme
C4471|'*adı*': kapsamsız bir numaralandırmanın İleri dönük bildiriminin bir temel türü (int varsayıldı) olmalıdır
C4472|'*adı*' yerel bir numaralandırma: bir yönetilen/WinRT numaralandırma bildirmek için bir erişim belirticisi (private/public) Ekle
C4492|'*türü*': taban başvuru sınıfı yöntemiyle eşleşiyor '*türü*', ancak 'override' işaretli değil
C4493|Delete ifadenin etkisi yok edicisinde '*türü*' 'public' erişilebilirlik yok
C4585|'*türü*': bir 'public ref class' korumalı olmalı veya varolan bir türetilen WinRT korumasız sınıfı
C4586|'*türü*': 'Windows' adlı bir üst düzey ad alanında ortak bir tür olarak bildirilemez
C4695|#pragma execution_character_set: '*bağımsız değişken*' desteklenen bir bağımsız değişken değil: şu anda yalnızca 'UTF-8' destekleniyor
C4703|başlatılmayabilecek yerel işaretleyici değişken '*adı*' kullanılır
C4728|/ Yl-PCH başvurusu gerekli olduğu için seçeneği yoksayıldı
C4745|Geçici Erişim '*adı*' boyutu nedeniyle kabul edilemez
C4746|Geçici Erişim '*adı*' / volatile tabi olduğu:\<ISO\|ms > ayarı; iç işlevleri __iso_volatile_load depolama kullanmayı düşünün
C4872|concurrency::parallel_for_each için çağrı grafı derlenirken desteklenemeyen sıfıra bölme noktasına kayan: '*açıklama*'
C4880|gelen atama '*türü*'to'*türü*': bir işaretçi veya başvuru sabitliği hemen atama amp sınırlı işlevde tanımlanmayan davranışta sonuçlanabilir
C4881|Oluşturucu ve/veya yok edici tile_static değişkeni için çağrılmayacak '*türü*'
C4966|'*açıklama*' açıklama yoksayıldı, desteklenmeyen segment adı olan __code_seg ek açıklaması var
C4988|'*türü*': değişken sınıf/işlev kapsamının dışında bildirildi
C4989|'*açıklama*': türde çakışan tanımlar.

## <a name="warnings-introduced-in-visual-c-2010-compiler-version-16004021901"></a>Visual C++ 2010 (Derleyici sürümü 16.00.40219.01) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:15__.

|||
|-|-|
C4352|'*adı*': iç işlev zaten tanımlandı
C4573|kullanımı '*türü*' gerektirir derleyicinin 'this' ancak yakalamak için geçerli varsayılan yakalama modu izin vermediğinden
C4574|'*adı*'' 0'olacak şekilde tanımlanır': kullanmayı mı amaçlamıştınız ' #if *adı*'?
C4689|'*karakter*': #pragma detect_mismatch değerinde desteklenmeyen karakter; #pragma yoksayıldı
C4751|/ arch: AVX bayrağı satır içi ASM'de olan Intel(r) Streaming SIMD Extensions için geçerli değildir
C4752|Intel(r) Gelişmiş vektör uzantıları bulundu; uygun/arch: AVX bayrağını kullanmayı düşünün
C4837|Üçlü harf algılandı: '?? *karakter*'yerine'*karakter*'
C4986|'*bildirimi*': özel durum belirtimi, önceki bildirimle eşleşmiyor
C4987|standart olmayan uzantı kullanıldı: 'throw (...)'

## <a name="warnings-introduced-in-visual-c-2008-compiler-version-15002102208"></a>Visual C++ 2008 (Derleyici sürümü 15.00.21022.08) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:14__.

|||
|-|-|
C4396|'*türü*': işlev şablonunun bir özelleştirmesi için bir friend bildirimi başvurduğunda, satır içi belirtici kullanılamaz
C4413|'*bildirimi*': başvuru üyesi Oluşturucu çıktıktan sonra sürmeyen bir geçici başlatılır
C4491|'*açıklama*': geçersiz bir IDL sürümü biçimine sahip
C4603|'*adı*': Makro tanımlı değil veya tanımı, önceden derlenmiş üstbilgi kullanımından farklıdır
C4627|'*açıklama*': Ön derlenmiş üstbilgi kullanımı aranırken atlandı
C4750|'*açıklama*': işlev bir döngünün satır içine _alloca() değerine sahip
C4910|'*türü*': '__declspec(dllexport)' ve 'extern' açık bir örnek oluşturmada uyumsuz
C4985|'*bildirimi*': öznitelikler önceki bildirimde yok.

## <a name="warnings-introduced-in-visual-c-2005-compiler-version-140050727762"></a>Visual C++ 2005'te (Derleyici sürümü 14.00.50727.762) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:13__.

|||
|-|-|
C4000|Bilinmeyen uyarısı Lütfen Visual C++ Yardım menüsünde teknik destek komutunu seçin veya daha fazla bilgi için teknik destek Yardım dosyasını açın
C4272|'*türü*': __declspec(dllimport) olarak işaretlenmiş; bir işlev alırken yerel çağrı kuralı belirtmeniz gerekir.
C4333|'*ifade*': veri kaybı olan çok fazla miktarda sağa kaydırma
C4334|'*ifade*': 32-bit kaydırmanın sonucu örtük olarak 64 bite dönüştürüldü (64-bit kaydırmanın hedeflenen oldu mu?)
C4335|Mac dosya biçimi algılandı: Lütfen kaynak dosyayı DOS veya UNIX biçimine dönüştürün
C4342|davranış değişikliği: '*türü*' çağrıldı, ancak önceki sürümlerde bir üye işleç çağrılıyordu
C4350|davranış değişikliği: '*bildirimi*'yerine adlandırılan'*bildirimi*'
C4357|Temsilci biçimsel bağımsız değişken listesinde param dizisi bağımsız değişkeni bulundu '*bildirimi*'üretilirken yoksayıldı'*türü*'
C4358|'*ifade*': birleştirilmiş temsilcilerin dönüş türü 'void' değil; döndürülen değer tanımsız
C4359|'*türü*': hizalama belirleyici asıl hizalamadan küçük olduğundan (*numarası*) ve yoksayılacak.
C4362|'*türü*': 8 bayttan büyük hizalama CLR tarafından desteklenmiyor
C4364|# derleme için using '*adı*' daha önce görülme *açıklama*(*numarası*) as_friend özniteliği; as_friend uygulanmadı
C4365|'*ifade*': dönüştürme '*türü*'to'*türü*', imzalı/imzasız uyuşmazlığı
C4366|Birli sonucu '*işleci*' işleci hizalanmamış olabilir
C4367|Dönüştürme işlemi '*türü*'to'*türü*' veri türü hizalanmama özel durumuna neden olabilir
C4368|nelze definovat '*adı*'üyesi yönetilen olarak'*türü*': karma türler desteklenmiyor
C4369|'*türü*': Numaralandırıcı değeri '*numarası*'olarak gösterilemez'*türü*', değer'*sayı*'
C4374|'*bildirimi*': arabirim yöntemi sanal olmayan yöntemi tarafından uygulanmayacak '*bildirimi*'
C4375|Genel olmayan yöntemin '*bildirimi*'geçersiz '*bildirimi*'
C4376|erişim belirticisi '*belirticisi*:' artık desteklenmiyor: Lütfen kullanın '*belirticisi*:' yerine
C4377|Yerel türler varsayılan olarak özeldir; -d1PrivateNativeTypes kullanım dışıdır
C4378|Başlatıcıları çalıştırmak için işlev işaretçilerinin edinmeniz gerekir; :: resolvemethodhandle kullanmayı düşünün
C4379|Sürüm *sürüm* ortak dil çalışma zamanı Bu derleyici tarafından desteklenmiyor. Bu sürümün kullanılması beklenmeyen sonuçlara neden
C4381|'*bildirimi*': arabirim yöntemi ortak olmayan yöntemi tarafından uygulanmayacak '*bildirimi*'
C4382|özel durum atma '*türü*': __clrcall yok Edicisi veya kopya Oluşturucusu olan bir tür yalnızca/CLR yakalanabilir: pure modülünde
C4383|'*türü*': başvurusunu değiştirmenin anlamı kullanıcı tanımlı olduğunda değişebilir, '*işleci*' işleci var; işleci, işlenenin hakkında açık olmaya statik işlev olarak yazma
C4384|#pragma '*yönergesi*' yalnızca genel kapsamda kullanılmalıdır
C4393|'*türü*': const hiçbir etkisi olmaz *açıklama* veri üyesi; yoksayıldı
C4394|'*türü*': per-appdomain simgesi __declspec ile işaretlenmemelidir (*değer*)
C4395|'*türü*': üye işlev, initonly veri üyesinin bir kopyası üzerinde çağrılacak '*türü*'
C4397|DefaultCharSetAttribute yoksayıldı
C4398|'*türü*': başına-process genel nesnesi birden fazla AppDomain ile doğru çalışmayabilir; __declspec(appdomain) kullanmayı düşünün
C4399|'*türü*': işlem içi sembol __declspec ile işaretlenmemelidir (*değer*) / CLR ile derlendiğinde: Saf
C4400|'*türü*': Bu tür üzerindeki const/volatile niteleyicileri desteklenmiyor
C4412|'*bildirimi*': işlev imzası içeren tür '*türü*'; C++ nesnelerinin saf kod arasında geçirilmesi güvenli değildir ve karma veya yerel.
C4429|Olası eksik veya yanlış biçimlendirilmiş evrensel karakter adı
C4430|tür belirticisi eksik - int varsayıldı. Not: C++ varsayılan int desteklemez
C4431|tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor
C4434|bir statik oluşturucunun özel erişilebilirliği olmalıdır; özel erişim olarak değiştiriliyor
C4439|'*türü*': imzasında yönetilen bir tür olan işlev tanımında bir __clrcall çağrı kuralı olması gerekir
C4441|çağırma kuralı, '*kuralı*' yoksayıldı; '*kuralı*' yerine kullanılan
C4445|'*bildirimi*': bir yönetilen/WinRT türü sanal yöntem özel olamaz
C4460|CLR/WinRT işleci '*türü*', parametre geçirilen başvuruya göre sahip. CLR/WinRT işleci '*işleci*'C++ işleci farklı semantiğe sahip'*işleci*', değere göre geçirilecek kullanmak mı istiyordunuz?
C4461|'*türü*': Bu sınıfında bir Sonlandırıcı '! *tür*' ancak hiçbir yok edici ' ~*türü*'
C4470|kayan noktalı denetim pragma'ları / CLR altında yoksayılır
C4480|Standart olmayan uzantı kullanıldı: numaralandırma için temeldeki türü belirtme '*türü*'
C4481|Standart olmayan uzantı kullanıldı: geçersiz kılma belirticisi '*belirticisi*'
C4482|Standart olmayan uzantı kullanıldı: numaralandırma '*türü*' tam adında kullanılan
C4483|sözdizimi hatası: C++ anahtar sözcüğü bekleniyor
C4484|'*türü*': taban başvuru sınıfı yöntemiyle eşleşiyor '*türü*', ancak 'virtual', 'new' veya 'override'; işaretli değil 'new' (ve 'virtual' değil) varsayıldı
C4485|'*türü*': taban başvuru sınıfı yöntemiyle eşleşiyor '*türü*', ancak işaretlenen 'new' veya 'override'; 'new' (ve 'virtual') varsayıldı
C4486|'*türü*': bir başvuru sınıfının veya değer sınıfının özel bir sanal yöntemi 'sealed' olarak işaretlenmelidir
C4487|'*türü*': devralınan sanal olmayan yöntemiyle eşleşiyor '*türü*' ancak açıkça 'new' işaretli değil
C4488|'*türü*': gerektiren '*anahtar sözcüğü*'arabirim yöntemini uygulamak için anahtar sözcüğü'*türü*'
C4489|'*anahtar sözcüğü*': arabirim yöntemi üzerinde kullanılamaz '*adı*'; geçersiz kılma belirticileri yalnızca başvuru sınıfı ve değer sınıfı yöntemleri üzerinde izin verilir
C4490|'*anahtar sözcüğü*': geçersiz kılma belirticisi; yanlış kullanımı '*türü*' taban başvuru sınıfı yöntemiyle eşleşmiyor
C4538|'*türü*': Bu tür üzerindeki const/volatile niteleyicileri desteklenmiyor
C4559|'*türü*': yeniden tanımlama; işlev kazançlar __declspec (*değer*)
C4565|'*türü*': yeniden tanımlama; simge daha önce __declspec ile bildirildi (*değer*)
C4566|evrensel karakter-adı tarafından temsil edilen karakter '*karakter*' geçerli kod sayfasında temsil edilemeyen (*numarası*)
C4568|'*türü*': hiçbir üye açık geçersiz kılma imzayla eşleşmiyor
C4569|'*türü*': hiçbir üye açık geçersiz kılma imzayla eşleşmiyor
C4570|'*türü*': soyut ancak soyut işlevler içeriyor olarak açıkça bildirilmedi
C4571|Bilgi amaçlı: Visual C++ 7.1 sürümünden sonra değişti catch(...) semantiği; yapılandırılmış özel durumlar (SEH) artık yakalanmıyor
C4572|[ParamArray] özniteliği/CLR altında kullanım dışı bırakılmıştır, '...' kullanmak yerine
C4580|[attribute] Kullanımdan kalktı; Bunun yerine belirtin *belirtilen*bir temel sınıf olarak özniteliği
C4581|kullanımdan kalkan davranış: ' "*adı*"' yerine '*adı*' özniteliği işlemek için
C4606|#pragma uyarısı: '*sayı*' yoksayıldı; Kod çözümleme uyarıları, uyarı düzeyleriyle ilişkili değil.
C4631|MSXML veya XPath kullanılamıyor, XML belgesi açıklamaları işlenmeyecek. *açıklaması*
C4632|XML belgesi açıklaması: *açıklama* -erişim reddedildi: *açıklaması*
C4633|XML belgesi açıklaması*açıklama*: hata: *açıklaması*
C4634|XML belgesi açıklaması*açıklama*: uygulanamaz: *açıklaması*
C4635|XML belgesi açıklaması*açıklama*: hatalı oluşturulmuş XML: *açıklaması*
C4636|XML belgesi açıklaması*açıklama*: etiketi boş gerekli '*açıklama*' özniteliği.
C4637|XML belgesi açıklaması*açıklama*: \<dahil > Etiket atıldı. *açıklaması*
C4638|XML belgesi açıklaması*açıklama*: Bilinmeyen sembole başvuru '*açıklama*'.
C4639|MSXML hatası, XML belgesi açıklamaları işlenmeyecek. *açıklaması*
C4641|XML belgesi açıklamasında belirsiz bir çapraz başvuru var:
C4678|temel sınıfı*bildirimi*'den daha az erişilebilir olan'*adı*'
C4679|'*açıklama*': üye alınamadı
C4687|'*türü*': kapalı bir soyut sınıf, arabirim uygulayamaz '*türü*'
C4688|'*adı*': sınırlama listesi derleme özel türünü içeriyor '*bildirimi*'
C4690|\[ emitidl (pop)]: atma sayısından fazla
C4691|'*türü*': başvurulan tür bekleniyordu başvurulmayan *Modülü* '*açıklama*', bunun yerine geçerli çeviri biriminde tanımlanan tür
C4692|'*adı*': özel üyenin olmayan imzası derleme özel yerel türünü içeriyor '*bildirimi*'
C4693|'*türü*': kapalı bir soyut sınıf tüm örnek üyeleri olamaz*adı*'
C4694|'*türü*': kapalı bir soyut sınıf temel sınıf olamaz*türü*'
C4720|Satır içi Birleştirici raporları: '*açıklama*'
C4721|'*açıklama*': iç öğe olarak kullanılamıyor
C4722|'*açıklama*': yok edici hiç dönmüyor, olası bellek sızıntısı
C4726|ARM arch4/4T yalnızca destekleyen ' < cpsr_f > veya < spsr_f >' değerini
C4727|Adlı PCH *adı* bulunan aynı zaman damgasına sahip *adı* ve *adı*.  İlk PCH kullanılıyor.
C4729|Akış grafı için çok büyük işlevi, uyarı tabanlı
C4730|'*açıklama*': mixing _m64 ve kayan nokta ifadeleri hatalı koda neden olabilir
C4731|'*açıklama*': çerçeve işaretçisi kaydı '*kaydetme*' satır içi derleme kodu tarafından değiştirildi
C4732|İç '*iç*' Bu mimaride desteklenmiyor
C4733|Satır içi asm 'FS:0 için' atama: işleyici güvenli bir işleyici olarak kayıtlı değil
C4734|64 binden fazla satır numaralarını bir COFF bilgisi bölümünde hata ayıklama; Modülü için COFF hata ayıklama satır numaraları vermeyi durdurun '*Modülü*'
C4738|32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı
C4739|değişkenine başvuru '*değişkeni*' depolama alanını aşıyor
C4740|veya satır içi asm kodunda dışarı akma, genel iyileştirmeyi bastırır
C4742|'*değişkeni*'farklı hizalamaya sahip'*konumu*'ve'*konumu*': *numarası* ve *numarası*
C4743|'*adı*'başka bir boyutu vardır'*konumu*'ve'*konumu*': *numarası* ve *numarası* bayt
C4744|'*adı*'farklı türüne sahip '*konumu*'ve'*konumu*': '*türü*'ve'*türü*'
C4747|Yönetilen çağırma '*türü*': yönetilen kod DLL giriş noktası ve DLL giriş noktasından ulaşılan çağrılar dahil olmak üzere, yükleyici kilidi altında çalışmayabilir
C4761|bağımsız değişkende integral boyutu uyuşmazlığı; dönüştürme sağlandı
C4764|Yakalama nesneleri 16 baytın üzerinde hizalanamaz
C4788|'*tanımlayıcı*': tanımlayıcı kesildi '*sayı*' karakter
C4789|Arabellek '*adı*' boyutunun *numarası* bayt taşması; *numarası* bayt uzaklığında başlayarak yazılacak *numarası*
C4801|Başvuru ile dönüş doğrulanabilir değil: *açıklaması*
C4819|Dosya geçerli kod sayfasında temsil edilemeyen bir karakter içeriyor (*numarası*). Dosyayı veri kaybını önlemek için Unicode biçiminde kaydedin
C4826|Dönüştürme işlemi '*türü*'to'*türü*' işaret genişletilmiş. Bu, beklenmeyen çalışma zamanı davranışına neden olabilir.
C4829|Büyük olasılıkla yanlış parametreler ana işlev. Göz önünde bulundurun ' int main (Platform::Array\<Platform::String ^ > ^ argv)'
C4835|'*türü*': dışarı aktarılan veriler için Başlatıcı, önce yönetilen kod ana bilgisayar derlemesinde yürütülene kadar çalıştırılmayacak
C4867|'*türü*': standart olmayan söz dizimi; Kullan '&' bir üyeye işaretçi oluşturmak için
C4936|Bu __declspec yalnızca/CLR veya/CLR ile derlendiğinde desteklenir: Saf
C4937|'*adı*'ve'*adı*'için bağımsız değişkenler olarak ayırt edilemiyor'*seçeneği*'
C4938|'*türü*': kayan nokta azaltma değişkeni, / FP altında tutarsız sonuçlara neden olabilir: strict veya #pragma fenv_access
C4939|#pragma vtordisp kullanım dışı ve Visual C++'ın gelecek sürümde kaldırılacak.
C4947|'*türü*': eski olarak işaretlendi
C4949|'managed' ve 'unmanaged' pragmaları yalnızca ile derlendikleri zaman anlamlıdır ' / clr [: option]'
C4950|'*türü*': eski olarak işaretlendi
C4955|'*açıklama*': alma yoksayıldı; zaten içeri aktarılan '*kaynak*'
C4956|'*türü*': Bu tür doğrulanabilir değil
C4957|'*ifade*': açık tür dönüştürme gelen '*türü*'to'*türü*' doğrulanabilir değil
C4958|'*ifade*': işaretçi aritmetik doğrulanabilir değil
C4959|Yönetilmeyen tanımlanamaz *sınıfı* '*türü*' / CLR: safe, üyelerine erişilmesi doğrulanamayan bir koda neden olduğu
C4960|'*açıklama*' profili çok büyük
C4961|Hiç profil verisi içine birleştirildiği '*konumu*', profil temelli iyileştirmeler devre dışı bırakıldı
C4962|'*açıklama*': iyileştirmeler profil verilerinin tutarsız olmasına yol açtığı için devre dışı profil temelli iyileştirmeler
C4963|'*açıklama*': Profil verileri bulunamadı; işaretlenmiş yapımda farklı derleyici seçenekleri kullanılmış
C4964|İyileştirme seçeneği belirtilmedi; profil bilgileri toplanmayacak değil
C4965|örtük 0 tamsayı kutusunu; nullptr veya açık tür dönüştürme kullanın
C4970|temsilci oluşturucusu: hedef nesne yoksayıldı beri '*bildirimi*' statik
C4971|Bağımsız değişken sırası: \<hedef nesne >, \<hedef işlev > temsilci Oluşturucu kullanım dışı bırakılmıştır, kullanın \<hedef işlev >, \<hedef nesne >
C4972|Doğrudan değiştirme ya da açma işleminin sonucu lvalue olarak değerlendirmek doğrulanamaz

## <a name="warnings-introduced-in-visual-c-2003-compiler-version-13103077"></a>Visual C++ 2003'te (Derleyici sürümü 13.10.3077) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:13.00.9466__.

|||
|-|-|
C4343|#pragma en iyi duruma getirme (*açıklama*, kapalı) /Og seçeneğini geçersiz kılar
C4344|davranış değişikliği: açık şablon bağımsız değişkenleri çağrısıyla sonuçlandı kullanımını '*bildirimi*'
C4346|'*türü*': bağımlı öğe adı bir tür değil
C4348|'*bildirimi*': Varsayılan parametrenin yeniden tanımlanması: parametre *numarası*
C4356|'*türü*': statik veri üyesi türetilmiş sınıf aracılığıyla başlatılamaz
C4408|Anonim *yapı* herhangi bir veri üyesi bildirmiyor
C4544|'*bildirimi*': varsayılan şablon bağımsız değişkeni bu şablon bildiriminde yok sayıldı
C4545|virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor
C4546|virgülden önceki işlev çağrısında bağımsız değişken listesi eksik
C4547|'*ifade*': virgülden önceki etkisi yok; işleci yan etkisi olan beklenen işleci
C4548|virgülden önceki ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu
C4549|'*ifade*': virgülden önceki işlecin etkisi yok; kullanmak mı istiyordunuz '*ifade*'?
C4628|-Ze ile digraf kullanılması desteklenmez. Karakter dizisi '*dizisi*'için alternatif bir belirteç olarak yorumlanmadı'*belirteci*'
C4629|Digraph kullanıldığında, karakter dizisi '*dizisi*'belirteci olarak yorumlanan'*belirteci*' (Bu değilse ise iki karakter arasına bir boşluk ekleyin)
C4671|'*açıklama*': kopya oluşturucusuna erişilemez
C4676|'*açıklama*': yok ediciye erişilemez
C4677|'*adı*': özel üyenin olmayan imzası derleme özel türünü içeriyor '*bildirimi*'
C4686|'*türü*': davranışta olası bir değişiklik, udt'de değişiklik iade çağırma kuralı
C4812|eski bildirim stili: Lütfen '*türü*::*adı*' yerine
C4813|'*türü*': bir arkadaş işlev yerel bir sınıfın önceden bildirilmiş olmalıdır
C4821|Unicode kodlama türü belirlenemiyor, Lütfen dosyayı (BOM) imzasıyla kaydedin
C4822|'*türü*': yerel sınıf üyesi işlevinde bir gövde yok
C4823|'*türü*': kullanır ancak sabitleme işaretçileri geriye doğru izlenen semantik etkin değil. / Eha kullanmayı düşünün
C4913|Kullanıcı tanımlı ikili işleç ',' var ancak hiçbir aşırı yüklemesi dönüştüremedi tüm işlenenler, varsayılan yerleşik ikili operatör ',' kullanılan
C4948|dönüş türü '*bildirimi*' karşılık gelen ayarlayıcının son parametre türüyle eşleşmiyor
C4951|'*açıklama*' profili beri işlevi profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir
C4952|'*açıklama*': program veritabanında profil verileri bulunamadı '*açıklama*'
C4953|Alınanın '*açıklama*' profili bu yana profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir
C4954|'*açıklama*': oluşturulmamış (__int64 geçiş ifadesi içeriyor)

## <a name="warnings-introduced-in-visual-c-2002-compiler-version-13009466"></a>Visual C++ 2002 (Derleyici sürümü 13.00.9466) uyarıları

Derleyici seçeneğini kullanarak bu uyarıları ve üzeri sürümlerde tüm uyarıları bastırılan __/Wv:12__.

|||
|-|-|
C4096|'*türü*': arabirim bir COM arabirimi değil; ıdl'ye değil
C4097|pragma parametresinin 'restore' olması bekleniyor veya 'off'
C4165|'HRESULT' 'bool'; dönüştürülüyor budur başlatmak için istediğinize emin misiniz?
C4183|'*adı*': dönüş türü eksik; 'int' döndüren bir üye işlev olduğu varsayıldı
C4199|*açıklaması*
C4255|'*adı*': hiçbir işlev prototipi verilmedi: '(') '(void)' olarak dönüştürülüyor
C4256|'*bildirimi*': sanal tabanları olan sınıfın oluşturucusunda '...' var; çağrılar eski Visual C++ sürümleriyle uyumlu olmayabilir
C4258|'*adı*': tanımından döngü göz ardı edilir için; kapsayan kapsamdan gelen tanım kullanılır
C4263|'*bildirimi*': üye işlev hiçbir taban sınıfı sanal üye işlevini Geçersiz Kılmıyor
C4264|'*bildirimi*': taban sanal üye işlev için kullanılabilecek geçersiz kılma yok '*sınıfı*'; işlev gizlendi
C4265|'*türü*': sınıfın sanal işlevleri var ancak yok edici sanal değil, bu sınıfın örnekleri doğru şekilde edilmeyebilir
C4266|'*bildirimi*': taban sanal üye işlev için kullanılabilecek geçersiz kılma yok '*sınıfı*'; işlev gizlendi
C4267|'*ifade*': 'size_t' dönüştürme '*türü*', olası veri kaybı
C4274|#ident yoksayıldı; #pragma comment (exestr, 'string') için belgelere bakın
C4277|içeri aktarılan öğe '*türü*::*adı*' hem veri üyesi hem de işlev üyesi; olarak mevcut veri üyesi yoksayıldı
C4278|'*adı*': tür kitaplığındaki tanımlayıcı '*açıklama*' zaten bir makro; 'rename' niteleyicisini kullanın
C4279|'*adı*': tür kitaplığındaki tanımlayıcı '*açıklama*' bir anahtar sözcük; 'rename' niteleyicisini kullanın
C4287|'*ifade*': işaretsiz/negatif sabit uyuşmazlığı
C4288|Standart olmayan uzantı kullanıldı: '*adı*': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor; dış kapsamdaki bildirimiyle çakışıyor
C4289|Standart olmayan uzantı kullanıldı: '*adı*': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor
C4293|'*ifade*': kaydırma sayısı negatif veya çok büyük; tanımsız davranış
C4295|'*türü*': dizi Sonlandırıcı null karakterini içeremeyecek kadar küçük
C4296|'*ifade*': ifade her zaman olduğu *değeri*
C4297|'*türü*': işlev kabul ancak bir özel durum oluşturması beklenmiyor
C4298|'*adı*': tür kitaplığındaki tanımlayıcı '*açıklama*' zaten bir makrodur; yeniden adlandırma ' __*adı*'
C4299|'*adı*': tür kitaplığındaki tanımlayıcı '*açıklama*' bir anahtar sözcük; yeniden adlandırma ' __*adı*'
C4302|'*ifade*': kesildi '*türü*'to'*türü*'
C4303|*Dönüştürme* gelen '*türü*'to'*türü*' olan kullanımdan kaldırıldı, static_cast, __try_cast veya dynamic_cast kullanın
C4314|Beklenen pragma parametresinin '32' veya '64' olması
C4315|'*türü*': üye 'this' işaretçisi '*türü*' hizalı değil *numarası* Oluşturucu tarafından beklendiği gibi
C4318|memset'e uzunluk olarak sıfır sabiti geçirme
C4319|'*ifade*': sıfır genişletme '*türü*'to'*türü*' daha büyük boyutlu
C4321|arabirimi için IID otomatik olarak oluşturma '*türü*'
C4322|otomatik olarak sınıfının bir CLSID üretiliyor*türü*'
C4323|sınıf için kaydedilen CLSID yeniden kullanma*türü*'
C4324|'*türü*': hizalama tanımlayıcısı nedeniyle yapının sonu dolduruldu
C4325|Standart bölümün öznitelikleri '*açıklama*' yoksayıldı
C4326|dönüş türü '*adı*'olmalıdır'*türü*'veya'*türü*'
C4327|'*ifade*': yöneltme hizalaması (*numarası*) sol büyük (*numarası*)
C4328|'*açıklama*': biçimsel parametresinin yöneltme hizalaması *numarası* (*numarası*) gerçek bağımsız değişken hizalama büyük (*numarası*)
C4329|numaralandırma üzerinde hizalama tanımlayıcısı yoksayılır
C4336|Çapraz başvurulan tür kitaplığı İçeri Aktar '*Kitaplığı*'almadan'*açıklama*'
C4337|Çapraz başvurulan tür kitaplığının '*Kitaplığı*'in'*açıklama*' otomatik olarak içeri aktarılıyor
C4338|#pragma *açıklama*: standart bölüm '*bölüm*' kullanılır
C4339|'*türü*': Tanımsız Tür algılandı CLR/WinRT meta verilerinde - bu türün kullanılması çalışma zamanı özel durumuna neden
C4353|Standart olmayan uzantı kullanıldı: işlev ifadesi olarak 0 sabiti.  Bunun yerine '__noop ' iç işlevini iç kullanın
C4370|'*bildirimi*': sınıfın düzeni önceki bir sürümünden daha iyi paketleme nedeniyle derleyici değişti
C4371|'*bildirimi*': sınıfın düzeni önceki bir üyesinin daha iyi paketleme nedeniyle derleyici sürümünden değişmiş olabilir '*üye*'
C4373|'*türü*': sanal işlev geçersiz*bildirimi*', önceki derleyici sürümleri Parametreler yalnızca const/volatile niteleyicileri farklıydı olduğunda kılmadı
C4387|'*açıklama*': kabul
C4389|'*ifade*': imzalı/imzasız uyuşmazlığı
C4391|'*bildirimi*': beklenen iç işlev için yanlış dönüş türü '*türü*'
C4392|'*bildirimi*': yanlış sayıda bağımsız değişken beklenen iç işlev için '*sayı*' bağımsız değişkenleri
C4407|farklı işaretçiden üyeye gösterimleri arasında tür dönüştürme; derleyici yanlış kod üretebilir
C4420|'*adı*': işleç kullanılamıyor, kullanarak '*adı*' kullanılıyor; çalışma zamanı denetimi zarar görmüş
C4440|çağırma kuralı yeniden tanımlanması '*açıklama*'to'*açıklama*' yoksayıldı
C4442|__annotation bağımsız değişkeninde null Sonlandırıcı eklenmiş.  Değer kesilecek.
C4444|'*adı*': en üst düzey '__unaligned' Bu bağlamda uygulanmadı
C4526|'*türü*': statik üye işlevini sanal işlevini geçersiz kılamaz '*bildirimi*' geçersiz kılma yoksayıldı, sanal işlev gizlenecek
C4531|C++ özel durum işleme Windows CE üzerinde kullanılamaz. Yapılandırılmış özel durum işleme kullanın
C4532|'*açıklama*': / atlama *son* blok sonlandırma işleme sırasında davranışı tanımsız
C4533|öğesinin başlatılması '*bildirimi*' tarafından atlandığını ' goto *bildirimi*'
C4534|'*bildirimi*' için varsayılan oluşturucu olmayacaktır *sınıfı* '*türü*' nedeniyle varsayılan bağımsız değişken
C4535|çağıran _set_se_translator() çağrısı/eha gerektirir
C4536|'*açıklama*': tür adı, meta veri sınırını aşıyor '*sayı*' karakter
C4537|'*bildirimi*': '.'UDT olmayan türe uygulandı
C4542|Nesil birleştirilen eklenmiş dosyanın üretilmesi atlanıyor yazamıyor *türü* dosya: '*filename*': *hata*
C4543|Eklenen metin özniteliği tarafından gizlenen ' hiçbir\_injected_text'
C4555|ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu
C4557|'__assume' etkisi içeriyor '*etkisi*'
C4558|işlenenin değerini '*numarası*' je mimo rozsah'*numarası* - *sayı*'
C4561|'__fastcall' ile uyumsuz ' / clr' seçeneği: '__stdcall' için dönüştürme
C4562|tam prototipi oluşturulmuş işlevler gereklidir ' / clr' seçeneği: '(') '(void)' olarak dönüştürülüyor
C4564|yöntemi '*adı*' ın *sınıfı* '*türü*'desteklenmeyen varsayılan parametre tanımlar'*parametre*'
C4584|'*türü*': taban sınıfı*bildirimi*'temel sınıfının zaten'*bildirimi*'
C4608|Birleşimin birden fazla üyesi başlatılıyor: '*türü*'ve'*türü*'
C4619|#pragma uyarısı: uyarı numarası'yok '*sayı*'
C4623|'*türü*': varsayılan oluşturucu örtük bir şekilde silindi olarak tanımlandı
C4624|'*türü*': yıkıcı örtük bir şekilde silindi olarak tanımlandı
C4625|'*türü*': kopya Oluşturucusu örtük bir şekilde silindi olarak tanımlandı
C4626|'*türü*': atama işleci örtük bir şekilde silindi olarak tanımlandı
C4645|'noreturn' ile bildirilen işlevde dönüş deyimi var
C4646|'noreturn' ile bildirilen işlevde void olmayan dönüş türüne sahip.
C4659|#pragma '*açıklama*': ayrılmış segmentinin kullanımında '*adı*' kullanımı #pragma açıklamasını (Bağlayıcı,...) davranışı tanımsız
C4667|'*bildirimi*': zorlanan örnek oluşturmayla eşleşen işlev şablonu tanımlanmadı
C4668|'*adı*'için '0' ile değiştirerek önişlemci makrosu olarak tanımlanmamış '*değer*'
C4669|'*ifade*': Güvenli olmayan dönüştürme: '*türü*' yönetilen WinRT türü nesnesi
C4674|'*adı*' 'static' olarak bildirilmeli ve tam olarak bir parametreye sahip
C4680|'*türü*': coclass varsayılan bir arabirim belirtmiyor
C4681|'*türü*': coclass olay kaynağı olan varsayılan bir arabirim belirtmiyor
C4682|'*türü*': [in] varsayarak, hiçbir parametre özniteliği belirtilmedi
C4683|'*bildirimi*': olay kaynağı olan bir 'out'-parametre; birden çok olay işleyicisi yakalarken dikkatli olun
C4684|'*açıklama*': uyarı!! öznitelik geçersiz kod oluşturmaya neden olabilir: dikkatli kullanın
C4685|bekleniyor ' >> ' bulundu ' >> ' şablon parametreleri ayrıştırılırken
C4700|başlatılmamış yerel değişken '*adı*' kullanılır
C4701|başlatılmayabilecek yerel değişken '*adı*' kullanılır
C4702|erişilemeyen kodları
C4711|İşlev '*adı*' otomatik satır içi genişletme için seçilen
C4714|İşlev '*bildirimi*' __forceinline olarak satır içine alınmış işaretlenen
C4715|'*işlevi*': tüm denetim yolları değer döndürmez
C4716|'*işlevi*': bir değer döndürmelidir
C4717|'*işlevi*': özyinelemeli tüm denetim yollarında işlevi neden çalışma zamanı yığın taşması
C4718|'*işlevi*': özyinelemeli çağrının silme hiçbir yan etkisi vardır
C4719|Qfast belirtildiğinde - Kullan 'f' tek duyarlılık belirtmek için bir sonek olarak bulunan çift sabiti
C4723|olası 0 ile bölme
C4724|olası 0 ile mod
C4725|yönerge bazı Pentium'larda yanlış olabilir.
C4757|alt simge büyük bir imzalanmamış değer, negatif bir sabit mi istiyorsunuz?
C4772|#import eksik tür kitaplığından bir tür başvurulan; '*açıklama*' yer tutucu olarak kullanılan
C4792|İşlev '*işlevi*' sysimport kullanılarak bildirilen ve başvurulan yerel koddan; içeri aktarma kitaplığı gerekli bağlamak için
C4794|iş parçacığı yerel depolama değişkeninin segmenti '*adı*'değeri'*segment*'to'*segment*'
C4798|p-code işlevi için oluşturulan yerel kod '*adı*' özel durum işleyicisi veya semantikle
C4799|İşlev '*adı*' EMMS yönergesi yok
C4803|'*bildirimi*': yükseltme yönteminde olayın bir farklı depolama sınıfı olan '*bildirimi*'
C4810|pragma paketi(show) değeri == *numarası*
C4811|pragma değerini uyumluluk (forscope, show) == *değeri*
C4820|'*türü*': '*numarası*' bayt doldurma eklenen sonra *türü* '*türü*'
C4905|geniş dize sabit değeri için cast '*türü*'
C4906|dize sabit değeri için cast '*türü*'
C4912|'*özniteliği*': özniteliği bir iç içe geçmiş UDT'de davranışı tanımlı değil
C4916|dispid değerine sahip olmak için '*türü*': arabirim tarafından sunulan gerekir
C4917|'*türü*': bir GUID yalnızca bir sınıf, arabirim veya ad alanı ile ilişkilendirilebilir.
C4918|'*karakter*': pragram iyileştirme listesinde geçersiz karakter
C4920|Enum *adı* üye *adı*=*numarası* numaralandırmasında zaten görüldü *adı* olarak *adı* = *numarası*
C4921|'*adı*': öznitelik değeri '*değer*' birden çok kez belirtilmesi
C4925|'*bildirimi*': dispinterface yöntemi betikten çağrılamaz
C4926|'*bildirimi*': simge zaten tanımlandı: öznitelikler yoksayıldı
C4927|hatalı dönüştürme; birden fazla kullanıcı tanımlı dönüştürme örtük olarak uygulandı
C4928|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı
C4929|'*açıklama*': tür kitaplığı bir birleşim içeriyor; 'embedded_idl' niteleyicisi yoksayılıyor
C4930|'*bildirimi*': prototipli işlev çağrılmadı (değişken bir tanım hedeflenen oldu mu?)
C4931|tür kitaplığını oluşturulduğu varsayıyoruz *numarası*-bit işaretçiler
C4932|__tanımlayıcı (*açıklama*) ve __tanımlayıcı (*açıklama*) ayırt edilemiyor
C4934|'__delegate(multicast)' kullanım dışı, bunun yerine ' __delegate' kullanın
C4935|derleme erişim belirticisi değiştiren gelen '*açıklama*'
C4944|'*adı*': değerinden simge alınamıyor '*kaynak*': farklı*bildirimi*' geçerli kapsamda zaten var.
C4945|'*adı*': değerinden simge alınamıyor '*kaynak*': farklı*bildirimi*'başka bir derleme zaten alınmış'*kaynak*'
C4946|reinterpret_cast ilgili sınıflar arasında kullanıldı: '*bildirimi*'ve'*bildirimi*'
C4995|'*adı*': ad kullanım dışı #pragma olarak işaretlendi
C4996|'*sorunu*': *açıklaması*
C4997|'*türü*': coclass COM arabirimi veya sahte arabirim uygulamıyor
C4998|BEKLENTİ başarısız oldu: *açıklama*(*numarası*)

## <a name="see-also"></a>Ayrıca bkz.

- [/Wv derleyici seçeneği](../../build/reference/compiler-option-warning-level.md)
- [Varsayılan olarak kapalı olan derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md)
- [warning](../../preprocessor/warning.md)
