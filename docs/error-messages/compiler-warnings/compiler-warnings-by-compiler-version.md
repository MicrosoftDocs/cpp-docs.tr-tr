---
title: Derleyici Uyarısı derleyici sürümüne göre | Microsoft Docs
ms.custom: ''
ms.date: 05/30/2018
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
ms.openlocfilehash: e40de8aa08ae12bb0389a113be4d6cbd51196f12
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704743"
---
# <a name="compiler-warnings-by-compiler-version"></a>Derleyici sürümüne göre derleyici uyarıları

Derleyici kullanarak belirttiğiniz bir sürüm sonra sunulan uyarıları gizleyebilirsiniz [/Wv](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği. Bu, yeni bir araç takımının sürüm tanıtır ve geçici olarak yeni uyarıları bastırma istediğinizde yapı işleminizin yönetmek için kullanışlıdır. Bu seçenek, yeni hata iletileri bastırmak değil. Tüm yeni uyarıları bastırma önermiyoruz kalıcı olarak! En yüksek normal uyarı düzeyinde, her zaman derleme öneririz __/W4__, kaldırıp __/Wv__ yapınızın mümkün olan en kısa sürede seçeneği.

Yeni uyarılar derleyici bu sürümlerinde sunulur:

| Ürün | Derleme sürüm numarası |
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
| Visual C++ 2017 sürüm 15,5 | 19.12.25830.0 |
| Visual C++ 2017 sürüm 15,6 | 19.13.26128.0 |
| Visual C++ 2017 sürüm 15.7 | 19.14.26428.0 |

Yalnızca birincil numarasını, birincil ve ikincil sayılar veya ana, ikincil, belirtin ve yapı numaralarını için __/Wv__ seçeneği. Derleyici belirtilen rakamla başlayamaz sürümleri eşleşen tüm uyarıları raporlar ve belirtilen sayıdan büyük sürümleri için tüm uyarıları bastırır. Örneğin, __/Wv:17__ içinde ya da Visual Studio 2012'in herhangi bir sürümü önce sunulan tüm uyarıları raporlar ve Visual Studio 2013 (sürüm 18) veya daha sonra tüm derleyici tarafından sunulan tüm uyarıları bastırır. Gizlemek için Visual Studio 2015'te tanıtılan uyarıları güncelleştirme 2 ve daha sonra kullanabileceğiniz __/Wv:19.00.23506__. Kullanım __/Wv:19.11__ tüm uyarıları herhangi bir Visual Studio 2017 sürüm 15,5 önce Visual Studio sürümünde sunulan ancak Visual Studio 2017 15,5 ve sonraki sürümleri sunulan uyarıları bastırır bildirilecek.

Aşağıdaki bölümlerde her kullanarak gizleyebilirsiniz Visual C++ sürümü tarafından sunulan Uyarılar listesinde __/Wv__ derleyici seçeneği. __/Wv__ seçeneği derleyici belirtilen sürümleri geçerler listelenmeyen, uyarıları bastırma olamaz.

## <a name="warnings-introduced-in-visual-c-2017-version-157-compiler-version-1914264280"></a>Visual C++ 2017 sürüm 15.7 (derleyici sürüm 19.14.26428.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.13__.

|||
|-|-|
C4642|'*sorunu*': Genel parametresini kısıtlamalarını içe aktarılamıyor '*parametresi*'
C5045|Bellek Yükü /Qspectre geçiş yaparsanız belirtilen için derleyici Spectre azaltma ekler

## <a name="warnings-introduced-in-visual-c-2017-version-156-compiler-version-1913261280"></a>Visual C++ 2017 sürüm 15,6 (derleyici sürüm 19.13.26128.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.12__.

|||
|-|-|
C5044|Komut satırı seçeneğiyle bir bağımsız değişken *seçeneği* bir yola işaret eden '*yolu*' varolmayan

## <a name="warnings-introduced-in-visual-c-2017-version-155-compiler-version-1912258300"></a>Visual C++ 2017 sürüm 15,5 (derleyici sürüm 19.12.25830.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.11__.

|||
|-|-|
C4843|'*type1*': başvuru dizi veya işlev türü için bir özel durum işleyici erişilemiyor, kullanın '*type2*' yerine
C4844|' modülü dışarı *module_name*;' bir modül arabirimi bildirmek için tercih edilen sözdizimi sunulmuştur
C5039|'*işlevi*': - EHc altında extern C işlev işaretçisi veya potansiyel olarak işlevi atma başvuru geçirilen. Bu işlev bir özel durum oluşturursa tanımsız davranış ortaya çıkabilir.
C5040|dinamik özel durum belirtimleri yalnızca C ++ 14 ve daha önceki sürümlerde geçerli; noexcept(FALSE) değerlendirme
C5041|'*tanımı*': satır dışı tanım constexpr statik veri üyesi için gerekli değildir ve C ++ 17'de kullanım dışıdır
C5042|'*bildirimi*': blok kapsamında işlev bildirimleri standart C++'da belirtilen 'satır içi' olamaz; 'inline' tanımlayıcısı kaldırın
C5043|'*belirtimi*': özel durum belirtimi önceki bildirimi eşleşmiyor

## <a name="warnings-introduced-in-visual-c-2017-version-153-compiler-version-1911255060"></a>Visual C++ 2017 sürüm 15.3 (derleyici sürüm 19.11.25506.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.10__.

|||
|-|-|
C4597|Tanımsız davranış: *açıklaması*
C4604|'*türü*': bağımsız değişkeni değere göre yerel ve yönetilen sınırından geçirme geçerli kopya Oluşturucu gerektirir. Aksi halde çalışma zamanı davranışı tanımlı değil
C4749|Koşullu desteklenen: *açıklaması*
C4768|bağlantı belirtimi önce __declspec öznitelikleri göz ardı edilir
C4834|'nodiscard' özniteliğine sahip işlevinin dönüş değeri atılıyor
C4841|kullanılan standart uzantısı: *uzantısı*
C4842|'birden çok devralmayı kullanma türüne uygulanacağını offsetof' sonucunu derleyici sürümler arasında tutarlı olması garanti edilmez
C4869|'nodiscard' yalnızca sınıflar, numaralandırmalar ve dönüş türü void olmayan işlevleriyle uygulanabilir
C5033|'*depolama sınıfı*' artık desteklenen depolama sınıfı değil
C5034|biri iç kullanmak '*iç*' neden işlevi *işlevi* Konuk kodu olarak derlenecek
C5035|özelliğini kullanın '*özelliği*' neden işlevi *işlevi* Konuk kodu olarak derlenecek
C5036|VarArgs işlev işaretçisi dönüştürme /hybrid:x86arm64 ile derleme yapılırken '*type1*'to'*type2*'
C5037|'*üye işlevi*': sınıf şablonu üyesi satır dışı tanımını varsayılan bağımsız değişkenler sahip olamaz
C5038|veri üyesi '*Üye1*'veri üyesi sonra başlatılacak'*üye2*'

## <a name="warnings-introduced-in-visual-c-2017-rtm-compiler-version-1910250170"></a>Visual C++ 2017 RTM'de (derleyici sürüm 19.10.25017.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.00__.

|||
|-|-|
C4468|'fallthrough': durum etiketi veya varsayılan bir etiket özniteliği gelmelidir
C4698|'*özelliği*' değerlendirme yalnızca amacıyla ve değiştirilebilir veya gelecekte kaldırma güncelleştirir.
C4839|sınıfı standart kullanımını*sınıfı*' variadic işlevi bağımsız değişken olarak
C4840|sınıfı taşınabilir olmayan kullanımını*sınıfı*' variadic işlevi bağımsız değişken olarak

## <a name="warnings-introduced-in-visual-c-2015-update-3-compiler-version-1900242151"></a>Visual C++ 2015 güncelleştirme 3'te (derleyici sürüm 19.00.24215.1) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.00.23918__.

|||
|-|-|
C4467|ATL özniteliklerin kullanım dışı bırakılmıştır
C4596|'*adı*': üye bildiriminde geçersiz tam ad
C4598|' #include \< *üstbilgi*\>': üstbilgi numarası *numarası* içinde *kaynak* eşleşmiyor *kaynak* , adresindeki konumu
C4599|'*bağımsız değişkeni*': *kaynak* bağımsız değişken numarası *numarası* eşleşmiyor *kaynağı*

## <a name="warnings-introduced-in-visual-c-2015-update-2-compiler-version-1900239180"></a>Visual C++ 2015 güncelleştirme 2'de (derleyici sürüm 19.00.23918.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.00.23506__.

|||
|-|-|
C4466|Coroutine yığın elision gerçekleştirilemedi
C4595|'*sınıfı*': üye olmayan işleci yeni ya da silme işlevleri bildirilmemiş satır içi
C4828|Dosya Kaydır 0'dan başlayarak bir karakter içeriyor x*değeri* geçerli kaynak karakter kümesi geçersiz olan (codepage *numarası*).
C4868|Derleyici soldan sağa değerlendirme sırası küme ayracı içine alınan Başlatıcı listesindeki zorunlu değil

## <a name="warnings-introduced-in-visual-c-2015-update-1-compiler-version-1900235060"></a>Visual C++ 2015 güncelleştirme 1'de (derleyici sürüm 19.00.23506.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:19.00.23026__.

|||
|-|-|
C4426|en iyi duruma getirme bayrakları üstbilgisi de dahil olmak sonra değiştirilen #pragma optimize() nedeniyle olabilir
C4654|Kod önce yerleştirilmiş dahil önceden derlenmiş başlık satırı yok sayılacak. Kodu önceden derlenmiş üstbilgi ekleyin.
C5031|#pragma warning(pop): farklı bir dosya gönderilen uyarı durumuna pencerelerinin büyük olasılıkla uyuşmazlığı
C5032|#pragma warning(push) karşılık gelen hiçbir #pragma warning(pop) ile algılandı

## <a name="warnings-introduced-in-visual-c-2015-rtm-compiler-version-1900230260"></a>Visual C++ 2015 RTM ile (derleyici sürüm 19.00.23026.0) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:18__.

|||
|-|-|
C4427|'*hata*': sabit bölümdeki tanımsız davranış taşması
C4438|'*türü*': güvenle çağrılamaz / await: clrcompat modu. Varsa '*türü*' CLR çağrılar, CLR baş bozulmasına neden olabilir
C4455|' işleci *adı*': alt çizgi ile başlamıyor değişmez değer soneki tanımlayıcıları ayrılmıştır
C4456|bildirimi '*adı*' önceki yerel bildirimi gizler
C4457|bildirimi '*adı*' gizler işlev parametresi
C4458|bildirimi '*adı*' gizler üye sınıfı
C4459|bildirimi '*adı*' genel bildirim gizler
C4462|'*türü*': GUID türü belirlenemiyor. Program çalışma zamanında başarısız olabilir.
C4463|taşma; atama *değeri* değerleri yalnızca tutabileceği bit alanına *değeri* için *değeri*
C4473|'*işlevi*': yeterli sayıda bağımsız değişken geçirildi için biçim dizesi
C4474|'*işlevi*': çok fazla bağımsız değişken geçirildi için biçim dizesi
C4475|'*işlevi*': uzunluğu değiştiricisi '*değiştiricisi*'türü alan karakteriyle kullanılamaz'*karakter*' biçim belirticisi içinde
C4476|'*işlevi*': bilinmeyen tür alan karakteri '*karakter*' biçim belirticisi içinde
C4477|'*işlevi*': biçim dizesi '*dize*'türünde bir bağımsız değişken gerektirir'*türü*', ancak variadic bağımsız değişkeni *numarası* türüne sahip '*türü*'
C4478|'*işlevi*': konumsal ve konumsal dışı yer tutucuları aynı biçim dizesi karıştırılamaz
C4494|'*türü*': işlevi dönüş olduğundan türü __declspec(allocator) gözardı değil bir işaretçi veya başvuru
C4495|'__super' kullanılan standart olmayan uzantısı: açık temel sınıf adı ile değiştirin
C4496|Standart olmayan uzantı 'for each' kullanılan: aralıklı için deyimiyle değiştirin
C4497|'Kapalı' kullanılan standart olmayan uzantısı: 'Son' ile değiştir
C4498|kullanılan standart olmayan uzantısı: '*uzantısı*'
C4499|'*uzmanlık*': açık uzmanlık (göz ardı) depolama sınıfı olamaz
C4576|Başlatıcı listesi tarafından izlenen bir parantez içine alınmış bir standart açık tür dönüştürme sözdizimi türüdür
C4577|hiçbir özel durum işleme belirtilen modu ile kullanılan noexcept'; özel durum sonlandırıldığında garanti edilmez. /EHsc belirtin
C4578|'abs': dönüştürme '*türü*'to'*türü*', olası veri kaybını (çağırmak mu demek istediniz '*adı*' veya #include \<cmath >?)
C4582|'*türü*': Oluşturucu örtük olarak çağrılmaz
C4583|'*türü*': yıkıcı örtük olarak çağrılmaz
C4587|'*türü*': davranış değişikliği: Oluşturucusu artık dolaylı olarak çağrılır
C4588|'*türü*': davranış değişikliği: yıkıcı artık dolaylı olarak çağrılır
C4589|Soyut sınıf*türü*'Başlatıcısı sanal taban sınıfı için yoksayar'*türü*'
C4591|'constexpr' arama derinliği sınırını *numarası* aşıldı (/ constexpr:depth\<numarası >)
C4592|'*türü*': sembol dinamik olarak olacaktır (uygulama sınırlama) başlatıldı
C4593|'*türü*': 'constexpr' çağrısı değerlendirme adım sınırının *değeri* aşıldı; /constexpr:steps kullanın\<numarası > sınırını artırmak için
C4647|davranış değişikliği: __is_pod (*türü*) önceki sürümlerde farklı bir değere sahip
C4648|Standart özniteliği 'carries_dependency' göz ardı edilir
C4649|Bu bağlamda öznitelikleri göz ardı edilir
C4753|İşaretçi sınırları bulunamıyor; Göz ardı MPX iç işlevi
C4771|Sınırların bir basit işaretçisi kullanılarak oluşturulmalıdır; Göz ardı MPX iç işlevi
C4774|'*açıklama*': biçim dizesi bağımsız değişkeni beklenen *numarası* bir dize sabit değeri değil
C4775|Biçim dizesi içinde kullanılan standart olmayan uzantısı '*dize*'işlevinin'*işlevi*'
C4776|' %*karakter*'işlevinin biçim dizesi izin verilmez'*işlevi*'
C4777|'*açıklama*': biçim dizesi '*dize*'türünde bir bağımsız değişken gerektirir'*türü*', ancak variadic bağımsız değişkeni *numarası* türüne sahip '*türü*'
C4778|'*açıklama*': biçim dizesi Sonlandırılmamış '*dize*'
C4838|Dönüştürme '*türü*'to'*türü*' daraltma dönüştürme gerektirir
C5022|'*türü*': belirtilen birden çok taşıma oluşturucuları
C5023|'*türü*': belirtilen birden çok taşıma atama işleçleri
C5024|'*bildirimi*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma
C5025|'*bildirimi*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma
C5026|'*türü*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma
C5027|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma
C5028|'*adı*': hizalama önceki bildiriminde belirtilen (*numarası*) tanımı'nda belirtilmedi
C5029|kullanılan standart olmayan uzantısı: C++ hizalama öznitelikleri değişkenleri, veri üyeleri ve yalnızca etiket türleri için geçerlidir
C5030|öznitelik '*özniteliği*' tanınmıyor

## <a name="warnings-introduced-in-visual-c-2013-compiler-version-1800210051"></a>Visual C++ 2013 (derleyici sürüm 18.00.21005.1) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:17__.

|||
|-|-|
C4301|'*türü*': yalnızca sanal işlevi geçersiz kılma farklı olarak '*bildirimi*' const/volatile niteleyicisi tarafından
C4316|'*türü*': yığında ayrılmış nesne hizalı değil *numarası*
C4380|'*türü*': varsayılan bir oluşturucu kullanım
C4388|'*belirteci*': İmzalı ve imzasız uyuşmazlığı
C4423|'std::bad_alloc': sınıf tarafından yakalanan ('*türü*') satırındaki *numarası*
C4424|için catch '*türü*'öncesinde'*türü*' satırındaki *numarası*; öngörülemeyen 'std::bad_alloc' oluşturulursa davranışa neden olabilir
C4425|SAL ek açıklama uygulanamaz '...' için
C4464|göreli yol dahil içeren '..'
C4575|'__vectorcall' ile uyumsuz ' / clr' seçeneği: '__stdcall' dönüştürme
C4609|'*türü*'varsayılan arabiriminden türeyen'*türü*'type üzerinde'*türü*'. Kullanmak için farklı varsayılan arabirim '*türü*', veya temel ve türetilen ilişki bölün.
C4754|Buna karşılık aritmetik işlemler için dönüştürme kuralları *açıklama*(*numarası*), bir şube yürütülemez anlamına gelir. Cast '*türü*'to'*türü*' (veya benzer türde *numarası* bayt).
C4755|Buna karşılık aritmetik işlemler için dönüştürme kuralları *açıklama*(*numarası*), bir şube bir satır içi işlev yürütülemez anlamına gelir. Cast '*türü*'to'*türü*' (veya benzer türde *numarası* bayt).
C4767|Bölüm adı '*adı*' 8 karakterden uzun ve bağlayıcı tarafından kesilecek
C4770|enum'kısmen doğrulanmış '*adı*' dizini olarak kullanılır
C4827|Bir ortak 'ToString' yöntemi 0 parametrelerle sanal olarak işaretlenmesi gerekir ve geçersiz kılma
C4882|const olmayan çağrısı işleçleri ile functors concurrency::parallel_for_each için geçirme kullanım dışıdır
C4973|'*türü*': kullanım dışı olarak işaretlenmiş
C4974|'*türü*': kullanım dışı olarak işaretlenmiş
C4981|Warbird: işlev '*bildirimi*' __forceinline değil, özel durum semantiği içerdiğinden içermesinden işaretlenmiş.
C4990|Warbird: *iletisi*
C4991|Warbird: işlev '*bildirimi*' koruma düzeyini inlinee üst büyük olduğu için __forceinline içermesinden işaretlenmemiş
C4992|Warbird: işlev '*bildirimi*' korunamıyor satır içi derleme içerdiğinden __forceinline içermesinden işaretlenmemiş

## <a name="warnings-introduced-in-visual-c-2012-compiler-version-1700511061"></a>Visual C++ 2012 (derleyici sürüm 17.00.51106.1) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:16__.

|||
|-|-|
C4330|öznitelik '*özniteliği*'için bölüm'*bölüm*' yoksayıldı
C4415|Yinelenen __declspec (code_seg ('*adı*'))
C4416|__declspec(code_seg(...)) boş dize içeriyor: yoksayıldı
C4417|bir açık şablonu örneklemesi __declspec(code_seg(...)) olamaz: yoksayıldı
C4418|bir enum göz ardı __declspec(code_seg(...))
C4419|'*adı*'özel ref sınıfa uygulandığında etkisizdir'*türü*'.
C4435|'*türü*': nesne düzeni /vd2 altında nedeniyle sanal taban değiştirir '*türü*'
C4436|Sanal Taban gelen dynamic_cast '*türü*'to'*türü*' Oluşturucusu veya yıkıcı kısmen oluşturulmuş nesnesiyle başarısız olabilir
C4437|Sanal Taban gelen dynamic_cast '*türü*'to'*türü*' bazı bağlamlarda başarısız olabilir
C4443|'0', '1' veya '2' olması beklenen pragma parametresi
C4446|'*türü*': üye eşlenemiyor '*adı*' içinde bu tür, tür adı çakışması nedeniyle. Yöntemi, yeniden adlandırıldı '*adı*'
C4447|'ana' imzası iş parçacığı modeli olmadan bulundu. Kullanmayı ' int ana (Platform::Array\<Platform::String ^ > ^ args)'.
C4448|'*türü*' meta verilerinde belirtilmiş bir varsayılan arabirimine sahip değildir. Çekme: '*türü*', hangi çalışma zamanında başarısız olabilir.
C4449|'*türü*' korumasız bir türü '[WebHostHidden]' işaretlenmelidir
C4450|'*türü*'den türetilen olduğundan '[WebHostHidden]' işaretlenmelidir'*türü*'
C4451|'*türü*': ref sınıfı kullanımını*türü*' Bu bağlamda geçersiz nesnesinin bağlamlarında hazırlama açabilir iç
C4452|'*türü*': ortak türü, genel kapsamda olamaz. Bunun bir alt çıkış .winmd dosyasının adı olan bir ad alanında olması gerekir.
C4453|'*türü*': '[WebHostHidden]' türü değil genel bir tür yayımlanan yüzey üzerinde kullanılmamalıdır [WebHostHidden]
C4454|'*türü*' birden çok girdi parametresi sayısı tarafından belirtilen [DefaultOverload] gerek kalmadan aşırı yüklendi. Çekme '*bildirimi*' olarak varsayılan aşırı yüklemesi
C4471|'*adı*': dizininden kapsam dışı numaralandırma ileriye dönük bildirimi bir temel alınan türü (int olduğu varsayılır) olması gerekir
C4472|'*adı*' yerel Enum: yönetilen WinRT enum bildirmek için bir erişim belirteci (özel/ortak) Ekle
C4492|'*türü*': eşleşmeleri temel ref sınıf yöntemi '*türü*', 'override' işaretli değil ancak
C4493|DELETE ifadesi hiçbir etkisi yıkıcısı '*türü*' 'genel' erişilebilirlik yok
C4585|'*türü*': A 'ortak ref class' ya da korumalı olmalıdır veya mevcut bir türetilen WinRT korumasız sınıfı
C4586|'*türü*': 'Windows' adlı üst düzey bir ad alanında bir ortak türü bildirilemez
C4695|#pragma execution_character_set: '*bağımsız değişkeni*' desteklenen bir bağımsız değişken değil: şu anda yalnızca 'UTF-8' desteklenir
C4703|Potansiyel olarak başlatılmamış yerel işaretçi değişkeninin '*adı*' kullanılan
C4728|/ Yl-PCH başvurusu gerekli olduğundan yoksayıldı seçeneği
C4745|volatile erişimini '*adı*' boyutuna nedeniyle kabul edilemez
C4746|volatile erişimini '*adı*' / volatile tabi olan:\<ISO\|ms > ayarlama; __iso_volatile_load/deposu iç işlevler kullanmayı düşünün
C4872|Çağrı grafik concurrency::parallel_for_each için derleme sırasında algılanan sıfıra noktası bölme kayan: '*açıklama*'
C4880|gelen atama '*türü*'to'*türü*': hemen bir işaretçi veya reference constness atama sonuçlanabilir bir kısıtlanmış amp işlevinde tanımsız davranış
C4881|yapıcı ve/veya yıkıcı tile_static değişken için çağrılan değil '*türü*'
C4966|'*açıklama*' __code_seg ek açıklama desteklenmeyen segment adı, göz ardı ek açıklama sahip
C4988|'*türü*': değişken bildirilen dış sınıfı ya da işlevin kapsamı
C4989|'*açıklama*': çakışan tanımları türüne sahip.

## <a name="warnings-introduced-in-visual-c-2010-compiler-version-16004021901"></a>Visual C++ 2010 (derleyici sürüm 16.00.40219.01) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:15__.

|||
|-|-|
C4352|'*adı*': önceden tanımlanmış iç işlevi
C4573|kullanımını '*türü*' 'this' ancak yakalamak için derleyici gerektirir geçerli varsayılan yakalama modu izin vermediğinden
C4574|'*adı*'0 ' olarak tanımlanan': kullanılacak mu demek istediniz ' #if *adı*'?
C4689|'*karakter*': #pragma detect_mismatch desteklenmeyen bir karakter; göz ardı #pragma
C4751|/ arch AVX bayrağı ASM içi olan Intel(r) Streaming SIMD uzantıları için geçerli değildir
C4752|Intel(r) Gelişmiş vektör uzantıları bulundu; uygun/arch AVX bayrağı kullanmayı düşünün
C4837|trigrafı algılandı: '?? *karakter*'yerine'*karakter*'
C4986|'*bildirimi*': özel durum belirtimi önceki bildirimi eşleşmiyor
C4987|standart olmayan uzantı kullanıldı: 'throw (...)'

## <a name="warnings-introduced-in-visual-c-2008-compiler-version-15002102208"></a>Visual C++ 2008 (derleyici sürüm 15.00.21022.08) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:14__.

|||
|-|-|
C4396|'*türü*': bir arkadaş bildirimi işlevi şablonu özelleştirmesi için başvurduğunda satır içi belirticisi kullanılamaz
C4413|'*bildirimi*': başvuru üyesi Oluşturucusu çıktıktan sonra kalmıyor geçici bir başlatıldı
C4491|'*açıklama*': Geçersiz IDL sürüm biçimi
C4603|'*adı*': makrosu tanımlı değil ya da önceden derlenmiş üst bilgi kullandıktan sonra tanım farklı.
C4627|'*açıklama*': önceden derlenmiş üstbilgi kullanım aramakta zaman atlandı
C4750|'*açıklama*': _alloca() bir döngüye içermesinden ile işlevi
C4910|'*türü*': '__declspec(dllexport)' ve 'extern' üzerinde bir açık örnekleme uyumsuz
C4985|'*bildirimi*': öznitelikler önceki bildiriminde yok.

## <a name="warnings-introduced-in-visual-c-2005-compiler-version-140050727762"></a>Visual C++ 2005'te (derleyici sürüm 14.00.50727.762) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:13__.

|||
|-|-|
C4000|Lütfen bilinmeyen uyarı Visual C++ Yardım menüsünden teknik destek komut seçin veya daha fazla bilgi için teknik destek Yardım dosyasını açın
C4272|'*türü*': __declspec(dllimport) işaretlenmiş; yerel çağırma bir işlev içeri aktarırken belirtmeniz gerekir.
C4333|'*ifade*': çok büyük bir miktarını, veri kaybı tarafından sağa kaydırma
C4334|'*ifade*': 32-bit kaydırma sonucunu örtük olarak dönüştürülen 64 bit (64-bit kaydırma hedeflenen oldu mu?)
C4335|Mac dosya biçimi algılandı: Lütfen kaynak dosyasını DOS veya UNIX biçimine Dönüştür
C4342|davranış değişikliği: '*türü*' çağrılır, ancak üye işleci önceki sürümlerde çağrıldı
C4350|davranış değişikliği: '*bildirimi*'yerine adında'*bildirimi*'
C4357|param dizisi bağımsız bulunan temsilci için biçimsel bağımsız değişken listesinde '*bildirimi*'oluşturulurken göz ardı'*türü*'
C4358|'*ifade*': birleştirilmiş temsilciler dönüş türü 'void' değil; döndürülen değer tanımlanmadı
C4359|'*türü*': hizalama tanımlayıcısı, gerçek hizalama değerinden (*numarası*) ve göz ardı edilir.
C4362|'*türü*': hizalama 8 bayttan büyük CLR tarafından desteklenmiyor
C4364|# derleme için using '*adı*' konumunda önceden görülen *açıklama*(*numarası*) as_friend özniteliği olmadan; as_friend uygulanmaz
C4365|'*ifade*': dönüştürme '*türü*'to'*türü*', imzalı ve imzasız uyuşmazlığı
C4366|Tekli sonucunu '*işleci*' işleci hizalanmamış
C4367|Dönüştürme '*türü*'to'*türü*' datatype uyuşmazlığın özel durumuna neden olabilir
C4368|tanımlayamazsınız '*adı*'üyesi yönetilen olarak'*türü*': karışık türleri desteklenmiyor
C4369|'*türü*': Numaralayıcı değeri '*numarası*'olarak temsil edilemez'*türü*', değer'*numarası*'
C4374|'*bildirimi*': arabirim yöntemi uygulanmadı sanal olmayan yöntemi tarafından '*bildirimi*'
C4375|genel yöntem '*bildirimi*'geçersiz '*bildirimi*'
C4376|belirleyici erişmek '*belirticisi*:' artık desteklenmiyor: Lütfen kullanın '*belirticisi*:' yerine
C4377|Yerel türler varsayılan olarak özel; -d1PrivateNativeTypes kullanım dışı bırakıldı
C4378|İşlev işaretçileri başlatıcıları çalıştırmak için edinmeniz gerekir; System::ModuleHandle::ResolveMethodHandle göz önünde bulundurun
C4379|Sürüm *sürüm* ortak dil çalışma zamanı Bu derleyici tarafından desteklenmiyor. Bu sürümünü kullanarak beklenmeyen sonuçlara neden olabilir
C4381|'*bildirimi*': arabirim yöntemi uygulanmadı genel yöntemle '*bildirimi*'
C4382|atma '*türü*': / CLR __clrcall yıkıcı veya kopya Oluşturucu türüyle yalnızca yakalanabilir: Saf Modülü
C4383|'*türü*': bir tanıtıcı başvurusunun kaldırılmasının anlamı, kullanıcı tanımlı değiştirebilirler '*işleci*' var; işlenen hakkında açık olması için statik bir işlevi olarak işleci yazma işleci
C4384|#pragma '*yönergesi*' yalnızca genel kapsamda kullanılmalıdır
C4393|'*türü*': const hiçbir etkisi olmaz *açıklama* veri üyesi; göz ardı
C4394|'*türü*': appdomain başına simgesi işaretlenmemiş ile __declspec (*değeri*)
C4395|'*türü*': üye işlevi initonly veri üyesi bir kopyası üzerinde çağrılan '*türü*'
C4397|DefaultCharSetAttribute göz ardı edilir
C4398|'*türü*': işlem içi genel nesne ile birden çok appdomains oluşturuyor doğru çalışmayabilir; __declspec(appdomain) kullanmayı düşünün
C4399|'*türü*': işlem içi simgesi işaretlenmemiş ile __declspec (*değeri*) / CLR ile derlendiğinde: Saf
C4400|'*türü*': const/volatile niteleyicileri bu türü desteklenmiyor
C4412|'*bildirimi*': işlev imzası içeren türü '*türü*'; Saf kod arasında geçirmek için güvenli ve karma veya yerel C++ nesneleri.
C4429|Olası eksik veya hatalı oluşturulmuş evrensel karakter-adı
C4430|tür belirticisi eksik - int varsayıldı. Not: Varsayılan int C++ desteklemiyor
C4431|tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor
C4434|bir statik Oluşturucusu özel erişilebilirlik olması gerekir; özel erişimi değiştirme
C4439|'*türü*': İmzada yönetilen türü tanımıyla işlevi çağırma __clrcall olması gerekir
C4441|çağırma kuralı, '*kuralı*' göz ardı; '*kuralı*' yerine kullanılan
C4445|'*bildirimi*': bir yönetilen WinRT türünde sanal bir yöntem özel olamaz
C4460|CLR/WinRT işleci '*türü*', parametre geçtikten başvuruya göre. CLR/WinRT işleci '*işleci*'C++ işleci öğesinden farklı semantiklerine sahip'*işleci*', değere göre geçirilecek istiyordunuz?
C4461|'*türü*': Bu sınıf bir sonlandırıcı sahip '! *tür*', ancak hiçbir yıkıcı ' ~*türü*'
C4470|/ CLR altında göz ardı kayan nokta denetim pragmaları
C4480|kullanılan standart olmayan uzantısı: numaralandırma için temel alınan tür belirtme '*türü*'
C4481|kullanılan standart olmayan uzantısı: override tanımlayıcısı '*belirticisi*'
C4482|kullanılan standart olmayan uzantısı: enum '*türü*' tam adı kullanılan
C4483|sözdizimi hatası: C++ anahtar sözcüğü bekleniyor
C4484|'*türü*': eşleşmeleri temel ref sınıf yöntemi '*türü*', 'sanal', 'new' veya 'override'; işaretlenmemiş ancak 'Yeni' (ve 'sanal') kabul edilir
C4485|'*türü*': eşleşmeleri temel ref sınıf yöntemi '*türü*', ancak işaretlenen 'Yeni' veya 'override'; 'Yeni' (ve 'sanal') kabul edilir
C4486|'*türü*': özel sanal bir yöntem ref sınıfı veya değer sınıfı 'Kapalı' olarak işaretlenmelidir
C4487|'*türü*': eşleşmeleri devralınan sanal olmayan bir yöntem '*türü*' açıkça 'new' işaretlenmemiş ancak
C4488|'*türü*': gerektirir '*anahtar sözcüğü*'arabirim yöntemini uygulamak için anahtar sözcüğü'*türü*'
C4489|'*anahtar sözcüğü*': arabirim yöntemini verilmiyor '*adı*'; tanımlayıcıları yalnızca ref sınıfı ve değer sınıfı yöntemlere izin geçersiz kılma
C4490|'*anahtar sözcüğü*': geçersiz kılma tanımlayıcısı; yanlış kullanımı '*türü*' temel ref sınıf yöntemi eşleşmiyor.
C4538|'*türü*': const/volatile niteleyicileri bu türü desteklenmiyor
C4559|'*türü*': şemadaki; işlevi kazançlar __declspec (*değeri*)
C4565|'*türü*': şemadaki; simgenin __declspec ile önceden bildirildi (*değeri*)
C4566|evrensel karakter-adı tarafından temsil edilen karakter '*karakter*' geçerli kod sayfası gösterilemez (*numarası*)
C4568|'*türü*': hiçbir üye açık geçersiz kılma imza eşleşmesi
C4569|'*türü*': hiçbir üye açık geçersiz kılma imza eşleşmesi
C4570|'*türü*': soyut ancak soyut işlevleri taşıdığından açıkça bildirilmedi
C4571|Bilgi amaçlı: Visual C++ 7.1 beri değiştirilen catch(...) semantiği; yapılandırılmış özel durum (SEH) artık yakalandı
C4572|/ CLR altında [ParamArray] özniteliği kullanım dışı, '...' kullanmak yerine
C4580|[öznitelik] kullanım dışıdır; Bunun yerine belirtin *belirtilen*temel sınıf olarak özniteliği
C4581|davranış Kullanım: ' "*adı*"' yerine '*adı*' işlem özniteliği
C4606|#pragma uyarısı: '*numarası*' göz ardı; Kod çözümleme uyarıları uyarı düzeyleri ile ilişkili değil
C4631|MSXML veya XPath kullanılamaz, XML belge açıklamaları işlenmeyecek. *Açıklama*
C4632|XML belge açıklaması: *açıklama* -erişim reddedildi: *açıklaması*
C4633|XML belge açıklaması*açıklama*: hata: *açıklaması*
C4634|XML belge açıklaması*açıklama*: uygulanamaz: *açıklaması*
C4635|XML belge açıklaması*açıklama*: hatalı biçimlendirilmiş XML: *açıklaması*
C4636|XML belge açıklaması*açıklama*: etiketi boş gerekli '*açıklama*' özniteliği.
C4637|XML belge açıklaması*açıklama*: \<dahil > etiketi atılır. *Açıklama*
C4638|XML belge açıklaması*açıklama*: Bilinmeyen simgesi referansı '*açıklama*'.
C4639|MSXML hatası, XML belge açıklamaları işlenmeyecek. *Açıklama*
C4641|XML belge açıklamasında belirsiz bir çapraz başvuru var:
C4678|temel sınıfı*bildirimi*'den az erişilebilir olduğundan'*adı*'
C4679|'*açıklama*': üye içe aktarılamıyor
C4687|'*türü*': korumalı bir Özet sınıf bir arabirim uygulayamaz '*türü*'
C4688|'*adı*': kısıtlama listesini içeren derleme özel türü '*bildirimi*'
C4690|[ emitidl( pop ) ]: iter'den daha fazla POP
C4691|'*türü*': başvuru türü bekleniyordu başvurulmayan *Modülü* '*açıklama*', bunun yerine kullanılan geçerli çeviri biriminde tanımlanan türü
C4692|'*adı*': İmza özel olmayan üye olarak içeren derleme özel yerel tür '*bildirimi*'
C4693|'*türü*': korumalı bir Özet sınıf hiçbir örnek üyesinin olamaz*adı*'
C4694|'*türü*': korumalı bir Özet sınıf bir taban sınıfı olamaz*türü*'
C4720|Satır içi derleyici raporları: '*açıklama*'
C4721|'*açıklama*': bir iç olarak mevcut değil
C4722|'*açıklama*': yıkıcı hiçbir zaman döndürür, olası bellek sızıntısı
C4726|ARM arch4/4T destekler yalnızca ' < cpsr_f > veya < spsr_f >' hemen değeri ile
C4727|Adlı PCH *adı* bulunan aynı zaman damgasına sahip *adı* ve *adı*.  İlk PCH kullanma.
C4729|Uyarılar işlevi akış grafiği için çok büyük dayalı
C4730|'*açıklama*': _m64 karıştırma ve kayan nokta ifadeleri yanlış kodda neden olabilir
C4731|'*açıklama*': çerçeve işaretçisi Kaydet '*kaydetmek*' satır içi derleme kodu tarafından değiştirildi
C4732|İç '*iç*' Bu mimaride desteklenmiyor
C4733|Satır içi asm 'FS:0' atama: işleyici güvenli işleyici olarak kayıtlı değil
C4734|Birden fazla 64k bir COFF satır numaralarını bilgileri bölümünden hata ayıklama; COFF hata ayıklama satır numaralarını modülü için yayma Durdur '*Modülü*'
C4738|32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı
C4739|değişkeni referansı '*değişkeni*' kendi depolama alanını aşıyor
C4740|Akış içinde veya dışında satır içi asm kod genel en iyi duruma getirme gizler
C4742|'*değişkeni*'farklı hizalama sahip'*konumu*'ve'*konumu*': *numarası* ve *numarası*
C4743|'*adı*'farklı boyutuna sahip '*konumu*'ve'*konumu*': *numarası* ve *numarası* bayt
C4744|'*adı*'farklı türe sahip '*konumu*'ve'*konumu*': '*türü*'ve'*türü*'
C4747|Yönetilen çağırma '*türü*': yönetilen kod çalıştıramıyor DLL entrypoint ve DLL entrypoint ulaşıldı çağrıları dahil olmak üzere, yükleyici kilidi altında
C4761|bağımsız değişkende tam sayı boyutu uyuşmazlığı; sağlanan dönüştürme
C4764|16 bayttan büyük catch nesnelere hizalanamıyor
C4788|'*tanımlayıcısı*': tanımlayıcısı için kesildi '*numarası*' karakter
C4789|Arabellek '*adı*' boyutunun *numarası* bayt taşması; *numarası* bayt uzaklıkta başlayan yazılır *numarası*
C4801|Return başvurusu tarafından doğrulanabilen değil: *açıklaması*
C4819|Dosya geçerli kod sayfası gösterilemez bir karakter içeriyor (*numarası*). Unicode biçiminde veri kaybını önlemek için dosyayı kaydedin
C4826|Dönüştürme '*türü*'to'*türü*' oturum genişletilmiş olduğu. Bu, çalışma zamanı beklenmeyen davranışlara neden olabilir.
C4829|Büyük olasılıkla yanlış parametreler ana işlevi. Göz önünde bulundurun ' int ana (Platform::Array\<Platform::String ^ > ^ argv)'
C4835|'*türü*': yönetilen kod ilk ana bilgisayarı bütünleştirilmiş kodunda yürütülene dek dışarı aktarılan veriler için Başlatıcı çalıştırılmaz
C4867|'*türü*': standart sözdizimi; Kullan '&' üyesi için bir işaretçi oluşturmak için
C4936|Bu __declspec yalnızca/CLR veya/CLR ile derlendiğinde desteklenir: Saf
C4937|'*adı*'ve'*adı*'bağımsız değişken olarak ayırt olan'*seçeneği*'
C4938|'*türü*': kayan nokta azaltma değişkeni /fp altında tutarsız sonuçlara neden olabilir: katı veya #pragma fenv_access
C4939|#pragma vtordisp kullanım dışıdır ve Visual C++'ın bir sonraki sürümde kaldırılacak
C4947|'*türü*': kullanımdan kaldırılmış olarak işaretlenmiş
C4949|'yönetilen' ve 'yönetilmeyen' pragmaları yalnızca ile derlendiğinde anlamlı ' / clr [: seçeneği]'
C4950|'*türü*': kullanımdan kaldırılmış olarak işaretlenmiş
C4955|'*açıklama*': alma göz ardı; zaten içe '*kaynak*'
C4956|'*türü*': Bu tür doğrulanabilen değil
C4957|'*ifade*': açık dönüştürme '*türü*'to'*türü*' doğrulanabilen değil
C4958|'*ifade*': işaretçi aritmetiği doğrulanabilen değil
C4959|Yönetilmeyen tanımlayamazsınız *sınıfı* '*türü*' ın/CLR: safe üyelerine erişme doğrulanamayan kodu sağladığından
C4960|'*açıklama*' profili için çok büyük
C4961|Profil verilerini içine birleştirildiği '*konumu*', profil temelli iyileştirmeler devre dışı
C4962|'*açıklama*': Profil temelli iyileştirmeler iyileştirmeler profil verileri tutarsız hale gelmesine neden olduğundan devre dışı
C4963|'*açıklama*': farklı derleyici seçenekleri Araçlı derlemede kullanıldığını; hiçbir profil verileri bulundu
C4964|En iyi duruma getirme seçenekleri belirtildi; profil bilgileri toplanmaz
C4965|örtük kutusu tamsayı 0; nullptr veya açık atama kullanın
C4970|Oluşturucu temsilci: hedef nesne göz ardı itibaren '*bildirimi*' statik
C4971|Bağımsız değişken sipariş: \<hedef nesnesi >, \<hedef işlevi > temsilci Oluşturucu kullanım için kullanmak \<hedef işlevi >, \<hedef nesnesi >
C4972|Doğrudan değiştirerek veya bir unbox işleminin sonucu bir lvalue değerlendirmesini doğrulanamaz

## <a name="warnings-introduced-in-visual-c-2003-compiler-version-13103077"></a>Visual C++ 2003'te (derleyici sürüm 13.10.3077) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:13.00.9466__.

|||
|-|-|
C4343|#pragma en iyi duruma getirme (*açıklama*, kapalı) /Og seçeneğini geçersiz kılar
C4344|davranış değişikliği: açık şablon bağımsız değişken sonuçları çağrıda kullanımını '*bildirimi*'
C4346|'*türü*': bağımlı adı bir tür değil
C4348|'*bildirimi*': yeniden tanımlama varsayılan parametre: parametre *numarası*
C4356|'*türü*': statik veri üyesi türetilmiş sınıf başlatılamıyor
C4408|Anonim *yapısı* herhangi bir veri üyesi bildirme değil
C4544|'*bildirimi*': varsayılan bu şablonu bildiriminde göz ardı şablon bağımsız değişken
C4545|virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor
C4546|virgülden önceki işlev çağrısında bağımsız değişken listesi eksik
C4547|'*ifade*': virgülle; etkisizdir önce işleci yan etkisi olan beklenen işleci
C4548|virgülden önceki ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu
C4549|'*ifade*': işleci virgülle önce hiçbir etkisi; istiyordunuz '*ifade*'?
C4628|-Ze ile digraf kullanılması desteklenmez. Karakter dizisi '*dizisi*'alternatif belirteci için yorumlanan değil'*belirteci*'
C4629|Digraph kullanıldığında, bir karakter dizisi '*dizisi*'belirteci olarak yorumlanan'*belirteci*' (iki karakter arasında bir boşluk olmayan ne amaçladığınız buysa ekleyin)
C4671|'*açıklama*': kopya Oluşturucu erişilemiyor
C4676|'*açıklama*': yıkıcı erişilemiyor
C4677|'*adı*': İmza özel olmayan üye olarak içeren derleme özel türü '*bildirimi*'
C4686|'*türü*': olası değişiklik davranış UDT değişikliği iade çağırma
C4812|eski bildirim stili: Lütfen kullanın '*türü*::*adı*' yerine
C4813|'*türü*': yerel bir sınıfın arkadaş işlevi önceden bildirilmiş olmalıdır
C4821|Unicode kodlama türü belirlemek için lütfen dosyayı imza (BOM) ile kaydetmek için
C4822|'*türü*': yerel sınıf üye işlevi bir gövde yok
C4823|'*türü*': sabitleme işaretçileri ancak bırakma kullanır semantiği etkin değil. /EHa kullanmayı düşünün
C4913|Kullanıcı tanımlı ikili işleç ',' var, ancak hiçbir aşırı yüklemesi dönüştüremedi tüm işlenenler, varsayılan yerleşik ikili işleç ',' kullanılan
C4948|dönüş türü '*bildirimi*' karşılık gelen ayarlayıcı son parametre türü eşleşmiyor.
C4951|'*açıklama*' profili itibaren kullanılmıyor işlevi profil verileri, veri toplanmıştır düzenlenebilir
C4952|'*açıklama*': hiçbir profil verileri program veritabanında bulunan '*açıklama*'
C4953|Inlinee '*açıklama*' profili itibaren kullanılmıyor profil verileri, veri toplanmıştır düzenlenebilir
C4954|'*açıklama*': değil profili (__int64 anahtar ifadesi içerir)

## <a name="warnings-introduced-in-visual-c-2002-compiler-version-13009466"></a>Visual C++ 2002 (derleyici sürüm 13.00.9466) sunulan uyarıları

Bu uyarılar ve sonraki sürümlerinde tüm uyarıları derleyici seçeneği kullanılarak bastırılan __/Wv:12__.

|||
|-|-|
C4096|'*türü*': arabirim için IDL yayılan değil; bir COM arabirimi değil
C4097|Beklenen 'geri' olacak şekilde pragma parametresi veya 'off'
C4165|'Bool'; 'HRESULT' dönüştürülüyor Bu istediğinize emin misiniz?
C4183|'*adı*': dönüş türü; eksik 'int' döndürme üye işlevi varsayılır
C4199|*Açıklama*
C4255|'*adı*': verilen hiçbir işlev prototipi: dönüştürme '(void)' için ' (')
C4256|'*bildirimi*': sanal tabanları ile sınıf için bir oluşturucuya sahip '...'; çağrıları Visual C++ eski sürümleriyle uyumlu olmayabilir
C4258|'*adı*': tanımından döngü göz ardı için; çevreleyen kapsamdaki tanımından kullanılır
C4263|'*bildirimi*': üye işlevini geçersiz bir temel sınıf sanal üye işlevi
C4264|'*bildirimi*': temel sanal üyesi işlevinden için kullanılabilir geçersiz kılma '*sınıfı*'; işlevi gizli
C4265|'*türü*': sınıfı sanal işlevlere sahiptir, ancak yıkıcı sanal değil, bu sınıfın örnekleri değil destructed doğru
C4266|'*bildirimi*': temel sanal üyesi işlevinden için kullanılabilir geçersiz kılma '*sınıfı*'; işlevi gizli
C4267|'*ifade*': 'size_t' için bir dönüştürme '*türü*', olası veri kaybını
C4274|göz ardı #ident; #pragma Açıklama (exestr, 'string') belgelerine bakın
C4277|içeri aktarılan öğesi '*türü*::*adı*' veri üyesi hem işlevi üye; olarak mevcut göz ardı veri üyesi
C4278|'*adı*': tür kitaplığı tanımlayıcısı '*açıklama*' makro zaten; 'Yeniden Adlandır' niteleyicisi kullanın.
C4279|'*adı*': tür kitaplığı tanımlayıcısı '*açıklama*' bir anahtar sözcüktür; 'Yeniden Adlandır' niteleyicisi kullanın.
C4287|'*ifade*': İmzasız negatif sabit uyuşmazlığı
C4288|kullanılan standart olmayan uzantısı: '*adı*': for döngüsü denetim değişkeni için-döngüde bildirilen for döngüsü kapsamı dışında kullanılan; dış kapsamdaki bildirimiyle çakışıyor
C4289|kullanılan standart olmayan uzantısı: '*adı*': for döngüsü denetim değişkeni için-döngüde bildirilen for döngüsü kapsamı dışında kullanılır
C4293|'*ifade*': kaydırma sayısı negatif ya da çok büyük, undefined davranışı
C4295|'*türü*': dizidir sonlandırma bir null karakter dahil etmek için çok küçük
C4296|'*ifade*': ifadesidir her zaman *değeri*
C4297|'*türü*': işlevi kabul ancak bir özel durum yok
C4298|'*adı*': tür kitaplığı tanımlayıcısı '*açıklama*' makro zaten; için yeniden adlandırma ' __*adı*'
C4299|'*adı*': tür kitaplığı tanımlayıcısı '*açıklama*' bir anahtar sözcüktür; için yeniden adlandırma ' __*adı*'
C4302|'*ifade*': gelen kesilmesi '*türü*'to'*türü*'
C4303|*Dönüştürme* gelen '*türü*'to'*türü*' olan kullanım, static_cast, __try_cast veya dynamic_cast kullanın
C4314|'32' veya '64' olması beklenen pragma parametresi
C4315|'*türü*': 'this' üye işaretçisi '*türü*' hizalı değil *numarası* oluşturucusu tarafından beklendiği gibi
C4318|memset için sabit sıfır uzunluk olarak geçirme
C4319|'*ifade*': sıfır genişletme '*türü*'to'*türü*' büyük boyutu
C4321|bir IID arabirimi için otomatik olarak üretmek '*türü*'
C4322|sınıfı CLSID otomatik olarak üretmek*türü*'
C4323|sınıfı için kayıtlı CLSID yeniden kullanarak*türü*'
C4324|'*türü*': yapısı nedeniyle hizalama belirleyici doldurulan
C4325|Standart bölümü için öznitelikler '*açıklama*' yoksayıldı
C4326|dönüş türü '*adı*'olmalıdır'*türü*'veya'*türü*'
C4327|'*ifade*': LHS yöneltme hizalama (*numarası*) RHS büyük (*numarası*)
C4328|'*açıklama*': biçimsel parametresi yöneltme hizalamasını *numarası* (*numarası*) gerçek bağımsız değişkeni hizalama büyük (*numarası*)
C4329|Hizalama belirleyici enum göz ardı edilir
C4336|Çapraz referanslı tür kitaplığını içeri aktarma '*Kitaplığı*'almadan'*açıklama*'
C4337|Çapraz referanslı Tür Kitaplığı '*Kitaplığı*'in'*açıklama*' otomatik olarak içeri aktarılan
C4338|#pragma *açıklama*: standart bölüm '*bölüm*' kullanılır
C4339|'*türü*': Tanımsız Tür kullanımını algılandı CLR/WinRT meta veri - bu türün kullanımı, bir çalışma zamanı özel durumuna neden olabilir
C4353|kullanılan standart olmayan uzantısı: sabit 0 olarak işlev ifadesi.  Bunun yerine '__noop' işlevini iç kullanın
C4370|'*bildirimi*': sınıf yerleşimini daha iyi paketleme nedeniyle Derleyici önceki bir sürümünden değişti
C4371|'*bildirimi*': sınıf yerleşimini üyesinin daha iyi paketleme nedeniyle Derleyici önceki bir sürümünden değişmiş olabilir '*üye*'
C4373|'*türü*': sanal işlevi geçersiz kılma işlemleri*bildirimi*', önceki sürümlerini derleyici parametreleri yalnızca const/volatile niteleyicileri tarafından farklıydı olduğunda geçersiz
C4387|'*açıklama*': olarak kabul edildi
C4389|'*ifade*': İmzalı ve imzasız uyuşmazlığı
C4391|'*bildirimi*': beklenen iç işlevi için dönüş türü yanlış '*türü*'
C4392|'*bildirimi*': yanlış sayıda bağımsız değişken bekleniyor iç işlevi için '*numarası*' bağımsız değişkenleri
C4407|üye Beyanları farklı işaretçi arasında cast, derleyici yanlış kod oluşturabilirsiniz
C4420|'*adı*': kullanarak işleci kullanılamıyor, '*adı*' yerine; çalışma zamanı denetimi güvenliği aşılmış olabilir
C4440|gelen kuralı şemadaki çağırma '*açıklama*'to'*açıklama*' yoksayıldı
C4442|null Sonlandırıcı __annotation değişkeninde katıştırılmış.  Değer kesilir.
C4444|'*adı*': üst düzey '__unaligned' Bu bağlamda uygulanmadı
C4526|'*türü*': statik üye işlevi sanal işlevi geçersiz kılma olamaz '*bildirimi*' göz ardı, geçersiz kılma sanal işlev gizli
C4531|C++ özel durum işleme Windows CE mevcut değil. Yapılandırılmış özel durum işleme kullanın
C4532|'*açıklama*': dışı atlama *son* blok sonlandırma işleme sırasında davranışı tanımsız
C4533|Başlatma '*bildirimi*' tarafından Atlanan ' goto *bildirimi*'
C4534|'*bildirimi*' için varsayılan bir oluşturucu olmaz *sınıfı* '*türü*' varsayılan bağımsız değişkeni nedeniyle
C4535|Arama _set_se_translator() /EHa gerektirir
C4536|'*açıklama*': tür adı meta veri sınırını aşan '*numarası*' karakter
C4537|'*bildirimi*': '.'UDT olmayan türüne uygulanacağını
C4542|Birleştirilmiş eklenen metin dosyası oluşturma atlanıyor yazamıyor *türü* dosya: '*filename*': *hata*
C4543|Eklenen metin özniteliği tarafından gizlenen ' hiçbir\_injected_text'
C4555|ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu
C4557|'__assume' içeren etkisi '*etkisi*'
C4558|işlenen değerini '*numarası*'aralık dışında olduğundan'*numarası* - *numarası*'
C4561|'__fastcall' ile uyumsuz ' / clr' seçeneği: '__stdcall' dönüştürme
C4562|ile tam olarak örneklenmiş işlevler gereklidir ' / clr' seçeneği: dönüştürme '(void)' için ' (')
C4564|yöntemi '*adı*' ın *sınıfı* '*türü*'desteklenmeyen varsayılan parametre tanımlar'*parametresi*'
C4584|'*türü*': temel sınıf*bildirimi*'taban sınıfının zaten'*bildirimi*'
C4608|Birden çok üye birleşim başlatılıyor: '*türü*'ve'*türü*'
C4619|#pragma uyarısı: uyarı numarası yok '*numarası*'
C4623|'*türü*': varsayılan oluşturucu silindi olarak örtük olarak tanımlanmıştı
C4624|'*türü*': yıkıcı silindi olarak örtük olarak tanımlanmıştı
C4625|'*türü*': kopya Oluşturucu silindi olarak örtük olarak tanımlanmıştı
C4626|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı
C4645|'noreturn' ile bildirilen işlevi bir dönüş ifadesi içeriyor
C4646|'noreturn' ile bildirilen işlevi geçersiz kılma olmayan dönüş türüne sahip
C4659|#pragma '*açıklama*': ayrılmış kesimini kullanmak '*adı*' davranışı, kullanım #pragma Açıklama (Bağlayıcı,...) tanımsız
C4667|'*bildirimi*': eşleşen tanımlı hiçbir işlevi şablon zorlanmış örnek oluşturma
C4668|'*adı*'için '0' ile değiştirerek bir önişlemci makrosu olarak tanımlanmadığından'*değeri*'
C4669|'*ifade*': güvensiz dönüştürme: '*türü*' yönetilen WinRT type nesnesi
C4674|'*adı*' 'static' olarak bildirilmelidir ve tam olarak bir parametreye sahip
C4680|'*türü*': coclass'ı varsayılan arabirim değil belirtin
C4681|'*türü*': coclass değil, bir olay kaynağı varsayılan arabirimi belirtin
C4682|'*türü*': [in] varsayarak belirtilen yönlü parametre özniteliği yok
C4683|'*bildirimi*': olay kaynağı olan bir 'out'-parametre; alıştırma dikkatli birden çok olay işleyicileri takma
C4684|'*açıklama*': uyarı!! özniteliği geçersiz kod oluşturma neden olabilir: dikkatli kullanın
C4685|bekleniyor ' >> ' bulunan ' >> ' şablon parametreleri ayrıştırılırken
C4700|başlatılmamış yerel değişken '*adı*' kullanılan
C4701|Potansiyel olarak başlatılmamış yerel değişken '*adı*' kullanılan
C4702|koda erişilemiyor
C4711|İşlev '*adı*' otomatik satır içi genişletme için seçili
C4714|İşlev '*bildirimi*' __forceinline içermesinden işaretlenmemiş
C4715|'*işlevi*': değer tüm denetim yollarına döndürme
C4716|'*işlevi*': bir değer döndürmesi gerekir
C4717|'*işlevi*': Yinelenen tüm denetim yazmalar işlevi neden olacak çalışma zamanı yığın taşması
C4718|'*işlevi*': Özyinelemeli çağrı silme hiçbir yan etkisi vardır
C4719|Qfast belirtildiğinde - kullanım 'f' tek duyarlıklı belirtmek için sonek olarak bulunan çift sabiti
C4723|olası sıfıra bölünme 0
C4724|0 ile olası mod
C4725|yönerge üzerinde bazı Pentiums yanlış olabilir
C4757|alt simge büyük işaretsiz değer, negatif bir sabit istiyordunuz?
C4772|#import türü eksik bir tür kitaplığından başvurulan; '*açıklama*' yer tutucu olarak kullanılan
C4792|İşlev '*işlevi*' SysImport kullanılarak bildirilen ve başvurulan yerel koddan; içeri aktarma kitaplığını gerekli bağlamak için
C4794|iş parçacığı yerel depolama değişkenin Segment '*adı*'değiştirildi'*segment*'to'*segment*'
C4798|Yerel kod p-kodu işlevi için oluşturulan '*adı*' özel durum işleyici ile ya semantiğini geriye doğru izleme
C4799|İşlev '*adı*' EMMS yönerge olan
C4803|'*bildirimi*': artırma yöntemi, olay farklı depolama sınıfından sahip '*bildirimi*'
C4810|pragma pack(show) değerini == *numarası*
C4811|pragma değerini uygun (forScope, Göster) == *değeri*
C4820|'*türü*': '*numarası*' Doldurma bayt eklenen sonra *türü* '*türü*'
C4905|geniş dize sabit değeri için cast '*türü*'
C4906|dize sabit değeri için cast '*türü*'
C4912|'*özniteliği*': öznitelik iç içe geçmiş UDT davranışı tanımlı olmayan
C4916|bir DISPID olması için '*türü*': arabirim tarafından sunulan gerekir
C4917|'*türü*': GUID yalnızca bir sınıf, arabirim veya ad alanı ile ilişkilendirilebilir
C4918|'*karakter*': pragma iyileştirme listesinde geçersiz bir karakter
C4920|Enum *adı* üye *adı*=*numarası* zaten enum içindeki görülen *adı* olarak *adı* = *numarası*
C4921|'*adı*': öznitelik değeri '*değeri*' Çarp belirtilmemesi gerekir
C4925|'*bildirimi*': görüntüleme arabirimi yöntemi betikten çağrılamaz
C4926|'*bildirimi*': sembolü zaten tanımlandı: göz ardı öznitelikleri
C4927|Geçersiz dönüştürme; birden fazla kullanıcı tanımlı dönüştürme örtük olarak uygulanan
C4928|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı
C4929|'*açıklama*': typelibrary içerir; UNION 'embedded_idl' niteleyicisi yok sayılıyor
C4930|'*bildirimi*': çağrılmaz örneklenmiş işlevi (yönelik bir değişken tanımını oldu mu?)
C4931|tür kitaplığı için yapılmış varsayıyoruz *numarası*-bit işaretçileri
C4932|__tanımlayıcı (*açıklama*) ve __tanımlayıcı (*açıklama*) ayırt edilemeyen
C4934|'__delegate(multicast)' kullanım dışı bırakılmıştır, '__delegate anahtar bunun yerine' kullanın
C4935|derleme erişim belirticisi değiştiren '*açıklama*'
C4944|'*adı*': simgesini alamıyor '*kaynak*': as'*bildirimi*' geçerli kapsamda zaten var.
C4945|'*adı*': simgesini alamıyor '*kaynak*': as'*bildirimi*'başka bir derleme zaten alınmış'*kaynak*'
C4946|ilgili sınıflar arasında kullanılan reinterpret_cast: '*bildirimi*'ve'*bildirimi*'
C4995|'*adı*': ad, kullanım dışı #pragma işaretlendi
C4996|'*sorunu*': *açıklaması*
C4997|'*türü*': COM arabirimi veya Sahte Arabirimi coclass'ı uygulamıyor
C4998|BEKLENTİ başarısız oldu: *açıklama*(*numarası*)

## <a name="see-also"></a>Ayrıca bkz.

- [/Wv derleyici seçeneği](../../build/reference/compiler-option-warning-level.md)
- [Varsayılan olarak kapalı olan derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md)
- [warning](../../preprocessor/warning.md)
