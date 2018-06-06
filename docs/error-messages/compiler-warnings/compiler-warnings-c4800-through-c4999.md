---
title: Derleyici uyarıları C4800 C5999 aracılığıyla | Microsoft Docs
ms.date: 05/30/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4806
- C4807
- C4808
- C4809
- C4810
- C4811
- C4812
- C4813
- C4816
- C4817
- C4822
- C4825
- C4827
- C4837
- C4840
- C4841
- C4842
- C4843
- C4844
- C4872
- C4880
- C4881
- C4882
- C4900
- C4910
- C4912
- C4913
- C4916
- C4918
- C4920
- C4921
- C4925
- C4926
- C4932
- C4934
- C4935
- C4936
- C4937
- C4938
- C4939
- C4944
- C4947
- C4950
- C4951
- C4952
- C4953
- C4954
- C4955
- C4956
- C4957
- C4958
- C4959
- C4960
- C4961
- C4962
- C4963
- C4966
- C4970
- C4971
- C4972
- C4973
- C4974
- C4981
- C4985
- C4987
- C4988
- C4989
- C4990
- C4991
- C4992
- C4997
- C4998
- C4999
- C5022
- C5023
- C5024
- C5025
- C5026
- C5027
- C5028
- C5029
- C5030
- C5031
- C5032
- C5033
- C5034
- C5035
- C5036
- C5037
- C5039
- C5040
- C5041
- C5042
- C5043
- C5044
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06c4d65fe7b6ab2b0238c3a4e4cd081e2dc011b5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704756"
---
# <a name="compiler-warnings-c4800-through-c5999"></a>Derleyici uyarıları C4800 C5999 aracılığıyla

Bu bölümdeki makaleleri belgelerin derleyici tarafından üretilen uyarı iletilerini kümesini açıklayın.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>Uyarı iletileri

|Uyarı|İleti|
|-------------|-------------|
|[Derleyici Uyarısı (düzey 3) C4800](compiler-warning-level-3-c4800.md)|'*türü*': değer bool 'true' veya 'false' (Performans Uyarısı) zorlama|
|[Derleyici Uyarısı (düzey 1) C4803](compiler-warning-level-1-c4803.md)|'*yöntemi*': artırma yöntemi, olay farklı depolama sınıfından sahip '*olay*'|
|[Derleyici Uyarısı (düzey 1) C4804](compiler-warning-level-1-c4804.md)|'*işlemi*': işlem ' bool' türünün güvensiz kullanımı|
|[Derleyici Uyarısı (düzey 1) C4805](compiler-warning-level-1-c4805.md)|'*işlemi*': türü güvensiz karışımını '*type1*'ve türü'*type2*' işleminde|
|Derleyici Uyarısı (düzey 1) C4806|'*işlemi*': güvensiz işlemi: hiçbir değer türü '*type1*'türü için yükseltilen'*type2*' verilen sabiti eşit olabilir|
|Derleyici Uyarısı (düzey 1) C4807|'*işlemi*': türü güvensiz karışımını '*type1*'ve türü bit alanı imzalı'*type2*'|
|Derleyici Uyarısı (düzey 1) C4808|durumu '*değeri*' 'bool' anahtar koşul türü için geçerli bir değer değil|
|Derleyici Uyarısı (düzey 1) C4809|switch deyimi yedekli 'default' etiketi; yine de sahip istiyor musunuz? tüm olası 'case' etiketleri verilir.|
|Derleyici Uyarısı (düzey 1) C4810|pragma pack(show) değerini n ==|
|Derleyici Uyarısı (düzey 1) C4811|pragma değerini uygun (forScope, Göster) değeri ==|
|Derleyici Uyarısı (düzey 1) C4812|eski bildirim stili: Lütfen kullanın '*new_syntax*' yerine|
|Derleyici Uyarısı (düzey 1) C4813|'*işlevi*': yerel bir sınıfın arkadaş işlevi önceden bildirilmiş olmalıdır|
|Derleyici Uyarısı (düzey 4) C4816|'*param*': parametre (nesne başvurusu tarafından geçirilen sürece) bu kesilecek sıfır boyutlu bir dizi içeriyor|
|Derleyici Uyarısı (düzey 1) C4817|'*üye*': geçersiz kullanımı '.' Bu üye; erişmek için derleyici yerini '-> ile'|
|[Derleyici Uyarısı (düzey 1) C4819](compiler-warning-level-1-c4819.md)|Dosya geçerli kod sayfasında (sayı) gösterilemez bir karakter içeriyor. Unicode biçiminde veri kaybını önlemek için dosyayı kaydedin|
|[Derleyici Uyarısı (düzey 4) C4820](compiler-warning-level-4-c4820.md)|'*bayt*'Doldurma bayt eklenen sonra yapı'*member_name*'|
|[Derleyici Uyarısı (düzey 1) C4821](compiler-warning-level-1-c4821.md)|Unicode kodlama türü belirlemek için lütfen dosyayı imza (BOM) ile kaydetmek için|
|Derleyici Uyarısı (düzey 1) C4822|'üye işlevi': yerel sınıf üye işlevi bir gövde yok|
|[Derleyici Uyarısı (düzey 3) C4823](compiler-warning-level-3-c4823.md)|'*işlevi*': sabitleme işaretçileri ancak bırakma kullanır semantiği etkin değil. /EHa kullanmayı düşünün|
|Derleyici Uyarısı (Düzey 2) C4826|Dönüştürme '*type1*'to'*type2*' oturum genişletilmiş olduğu. Bu, çalışma zamanı beklenmeyen davranışlara neden olabilir.|
|Derleyici Uyarısı (Düzey 3) C4827|Bir ortak 'ToString' yöntemi 0 parametrelerle sanal olarak işaretlenmesi gerekir ve geçersiz kılma|
|[Derleyici Uyarısı (düzey 1) C4829](compiler-warning-level-1-c4829.md)|Büyük olasılıkla yanlış parametreler ana işlevi. Göz önünde bulundurun ' int ana (Platform::Array\<Platform::String ^ > ^ argv)'|
|[Derleyici Uyarısı (düzey 1) C4835](compiler-warning-level-1-c4835.md)|'*değişkeni*': yönetilen kod ilk ana bilgisayarı bütünleştirilmiş kodunda yürütülene dek dışarı aktarılan veriler için Başlatıcı çalıştırılmaz|
|Derleyici Uyarısı (düzey 4) C4837|trigrafı algılandı: '?? *karakter*'yerine'*karakter*'|
|[Derleyici Uyarısı (düzey 1) C4838](compiler-warning-level-1-c4838.md)|Dönüştürme '*type_1*'to'*type_2*' daraltma dönüştürme gerektirir|
|[Derleyici Uyarısı (Düzey 3) C4839](compiler-warning-level-3-c4839.md)|sınıfı standart kullanımını*türü*' variadic işlevi bağımsız değişken olarak|
|Derleyici Uyarısı (düzey 4) C4840|sınıfı taşınabilir olmayan kullanımını*türü*' variadic işlevi bağımsız değişken olarak|
|Derleyici Uyarısı (düzey 4) C4841|kullanılan standart uzantısı: offsetof içinde kullanılan bileşik üye göstergesi|
|Derleyici Uyarısı (düzey 4) C4842|'birden çok devralmayı kullanma türüne uygulanacağını offsetof' sonucunu derleyici sürümler arasında tutarlı olması garanti edilmez|
|C4843 uyarı derleyici|'*type1*': başvuru dizi veya işlev türü için bir özel durum işleyici erişilemiyor, kullanın '*type2*' yerine|
|C4844 uyarı derleyici|' modülü dışarı *module_name*;' bir modül arabirimi bildirmek için tercih edilen sözdizimi sunulmuştur|
|[Derleyici Uyarısı (hata) C4867](compiler-warning-c4867.md)|'*işlevi*': işlev çağrısı bağımsız değişken listesi eksik; bu değer '*çağrısı*' üyesi için bir işaretçi oluşturmak için|
|[Derleyici Uyarısı (düzey 4) C4868](compiler-warning-c4868.md)|'_dosya_(*line_number*)' derleyici zorla küme ayracı içine alınan başlatma listesinde soldan sağa değerlendirme sırası|
|Derleyici Uyarısı (Düzey 2) C4872|Çağrı grafik concurrency::parallel_for_each için derleme sırasında algılanan sıfıra noktası bölme kayan: '*konumu*'|
|Derleyici Uyarısı (düzey 1) C4880|gelen atama ' const *type_1*'to'*type_2*': hemen bir işaretçi veya reference constness atama sonuçlanabilir bir kısıtlanmış amp işlevinde tanımsız davranış|
|Derleyici Uyarısı (düzey 4) C4881|yapıcı ve/veya yıkıcı tile_static değişken için çağrılan değil '*değişkeni*'|
|Derleyici Uyarısı (düzey 1) C4882|const olmayan çağrısı işleçleri ile functors concurrency::parallel_for_each için geçirme kullanım dışıdır|
|C4900 uyarı derleyici|IL eşleşmiyorsa '*tool1*'version'*version1*'ve'*tool2*'version'*version2*'|
|[Derleyici Uyarısı (düzey 1) C4905](compiler-warning-level-1-c4905.md)|geniş düz dize 'LPSTR' değerine atandı|
|[Derleyici Uyarısı (düzey 1) C4906](compiler-warning-level-1-c4906.md)|düz dize 'LPWSTR' değerine atandı|
|Derleyici Uyarısı (düzey 1) C4910|'\<tanımlayıcısı >: '__declspec(dllexport)' ve 'extern' üzerinde bir açık örnekleme uyumsuz|
|Derleyici Uyarısı (düzey 1) C4912|'*özniteliği*': öznitelik iç içe geçmiş UDT davranışı tanımlı olmayan|
|Derleyici Uyarısı (düzey 4) C4913|Kullanıcı tanımlı ikili işleç ',' var, ancak hiçbir aşırı yüklemesi dönüştüremedi tüm işlenenler, varsayılan yerleşik ikili işleç ',' kullanılan|
|Derleyici Uyarısı (düzey 1) C4916|bir DISPID olması için '*açıklama*': arabirim tarafından sunulan gerekir|
|[Derleyici Uyarısı (düzey 1) C4917](compiler-warning-level-1-c4917.md)|'*bildirimcisi*': GUID yalnızca bir sınıf, arabirim veya ad alanı ile ilişkilendirilebilir|
|Derleyici Uyarısı (düzey 4) C4918|'*karakter*': pragma iyileştirme listesinde geçersiz bir karakter|
|Derleyici Uyarısı (düzey 1) C4920|Enum numaralandırma üyesi member_1 zaten enum enum içindeki member_2 görülen value_1 = value_2 =|
|Derleyici Uyarısı (Düzey 3) C4921|'*açıklama*': öznitelik değeri '*özniteliği*' Çarp belirtilmemesi gerekir|
|Derleyici Uyarısı (düzey 1) C4925|'*yöntemi*': görüntüleme arabirimi yöntemi betikten çağrılamaz|
|Derleyici Uyarısı (düzey 1) C4926|'*tanımlayıcısı*': sembolü zaten tanımlandı: göz ardı öznitelikleri|
|[Derleyici Uyarısı (düzey 1) C4927](compiler-warning-level-1-c4927.md)|Geçersiz dönüştürme; birden fazla kullanıcı tanımlı dönüştürme örtük olarak uygulanan|
|[Derleyici Uyarısı (düzey 1) C4928](compiler-warning-level-1-c4928.md)|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[Derleyici Uyarısı (düzey 1) C4929](compiler-warning-level-1-c4929.md)|'*dosya*': typelibrary içerir; UNION 'embedded_idl' niteleyicisi yok sayılıyor|
|[Derleyici Uyarısı (düzey 1) C4930](compiler-warning-level-1-c4930.md)|'*prototip*': çağrılmaz örneklenmiş işlevi (yönelik bir değişken tanımını oldu mu?)|
|[Derleyici Uyarısı (düzey 4) C4931](compiler-warning-level-4-c4931.md)|tür kitaplığının sayı bit işaretçiler için oluşturulduğunu varsayıyoruz|
|Derleyici Uyarısı (düzey 4) C4932|__tanımlayıcı (*tanımlayıcısı*) ve \__identifier (*tanımlayıcısı*) ayırt edilemeyen|
|Derleyici Uyarısı (düzey 1) C4934|'__delegate(multicast)' kullanım dışı bırakıldı, kullanın '\__delegate' yerine|
|Derleyici Uyarısı (düzey 1) C4935|derleme erişim belirticisi değiştiren '*erişim*'|
|Derleyici Uyarısı (düzey 1, hata) C4936|Bu __declspec yalnızca/CLR veya/CLR ile derlendiğinde desteklenir: Saf|
|Derleyici Uyarısı (düzey 4) C4937|'*Metin1*'ve'*Metin2*'bağımsız değişken olarak ayırt olan'*yönergesi*'|
|Derleyici Uyarısı (düzey 4) C4938|'*var*': kayan nokta azaltma değişkeni /fp altında tutarsız sonuçlara neden olabilir: katı veya #pragma fenv_access|
|C4939 uyarı derleyici|#pragma vtordisp kullanım dışıdır ve Visual C++'ın bir sonraki sürümde kaldırılacak|
|Derleyici Uyarısı (düzey 1) C4944|'*simgesi*': simgesini alamıyor '*assembly1*': as'*simgesi*' geçerli kapsamda zaten var.|
|[Derleyici Uyarısı (düzey 1) C4945](compiler-warning-level-1-c4945.md)|'*simgesi*': simgesini alamıyor '*assembly1*': as'*simgesi*'başka bir derleme zaten alınmış'*assembly2* '|
|[Derleyici Uyarısı (düzey 1) C4946](compiler-warning-level-1-c4946.md)|ilgili sınıflar arasında kullanılan reinterpret_cast: '*class1*'ve'*Ders2*'|
|Derleyici Uyarısı (düzey 1) C4947|'*type_or_member*': kullanımdan kaldırılmış olarak işaretlenmiş|
|[Derleyici Uyarısı (düzey 2) C4948](compiler-warning-level-2-c4948.md)|dönüş türü '*erişimci*' karşılık gelen ayarlayıcı son parametre türü eşleşmiyor.|
|[Derleyici Uyarısı (düzey 1 ve düzey 4) C4949](compiler-warning-level-1-and-level-4-c4949.md)|'yönetilen' ve 'yönetilmeyen' pragmaları yalnızca ile derlendiğinde anlamlı ' / clr [: seçeneği]'|
|Derleyici Uyarısı (düzey 1, hata) C4950|'*type_or_member*': kullanımdan kaldırılmış olarak işaretlenmiş|
|Derleyici Uyarısı (düzey 1) C4951|'*işlevi*' profili itibaren kullanılmıyor işlevi profil verileri, veri toplanmıştır düzenlenebilir|
|Derleyici Uyarısı (düzey 1) C4952|'*işlevi*': hiçbir profil verileri program veritabanında bulunan '*pgd_file*'|
|Derleyici Uyarısı (düzey 1) C4953|Inlinee '*işlevi*' profili itibaren kullanılmıyor profil verileri, veri toplanmıştır düzenlenebilir|
|C4954 uyarı derleyici|'*işlevi*': değil profili (__int64 anahtar ifadesi içerir)|
|C4955 uyarı derleyici|'*import2*': alma göz ardı; zaten içe '*import1*'|
|Derleyici Uyarısı (düzey 1, hata) C4956|'*türü*': Bu tür doğrulanabilen değil|
|Derleyici Uyarısı (düzey 1, hata) C4957|'*cast*': açık dönüştürme '*cast_from*'to'*cast_to*' doğrulanabilen değil|
|Derleyici Uyarısı (düzey 1, hata) C4958|'*işlemi*': işaretçi aritmetiği doğrulanabilen değil|
|Derleyici Uyarısı (düzey 1, hata) C4959|yönetilmeyen tür tanımlayamazsınız '*türü*' / CLR: safe içinde üyelerine erişme doğrulanamayan kodu sağladığından|
|Derleyici Uyarısı (düzey 4) C4960|'*işlevi*' profili için çok büyük|
|Derleyici Uyarısı (düzey 1) C4961|Profil verileri '.pgd dosyasına', profil temelli iyileştirmeler devre dışı birleştirilmiş|
|Derleyici Uyarısı (düzey 4) C4962|'*işlevi*': Profil temelli iyileştirmeler iyileştirmeler profil verileri tutarsız hale gelmesine neden olduğundan devre dışı|
|Derleyici Uyarısı (düzey 1) C4963|'*açıklama*': farklı derleyici seçenekleri Araçlı derlemede kullanıldığını; hiçbir profil verileri bulundu|
|[Derleyici Uyarısı (düzey 1) C4964](compiler-warning-level-1-c4964.md)|En iyi duruma getirme seçenekleri belirtildi; profil bilgileri toplanmaz|
|[Derleyici Uyarısı (düzey 1) C4965](compiler-warning-level-1-c4965.md)|örtük kutusu tamsayı 0; nullptr veya açık atama kullanın|
|Derleyici Uyarısı (düzey 1) C4966|'*işlevi*' __code_seg ek açıklama desteklenmeyen segment adı, göz ardı ek açıklama sahip|
|C4970 uyarı derleyici|Oluşturucu temsilci: hedef nesne göz ardı itibaren '*türü*' statik|
|Derleyici Uyarısı (düzey 1) C4971|Bağımsız değişken sipariş: \<hedef nesnesi >, \<hedef işlevi > temsilci Oluşturucu kullanım için kullanmak \<hedef işlevi >, \<hedef nesne = "" >|
|Derleyici Uyarısı (düzey 1, hata) C4972|Doğrudan değiştirerek veya bir unbox işleminin sonucu bir lvalue değerlendirmesini doğrulanamaz|
|Derleyici Uyarısı (düzey 1) C4973|'*sembol*': kullanım dışı olarak işaretlenmiş|
|Derleyici Uyarısı (düzey 1) C4974|'*sembol*': kullanım dışı olarak işaretlenmiş|
|Derleyici Uyarısı (Düzey 3) C4981|Warbird: işlev '*işlevi*' __forceinline değil, özel durum semantiği içerdiğinden içermesinden işaretlenmiş.|
|Derleyici Uyarısı (Düzey 3) C4985|sembol adını ': öznitelikler önceki bildiriminde yok.|
|[Derleyici Uyarısı C4986](compiler-warning-c4986.md)|'*bildirimi*': özel durum belirtimi önceki bildirimi eşleşmiyor|
|Derleyici Uyarısı (düzey 4) C4987|standart olmayan uzantı kullanıldı: 'throw (...)'|
|Derleyici Uyarısı (düzey 4) C4988|'*değişkeni*': değişken bildirilen dış sınıfı ya da işlevin kapsamı|
|Derleyici Uyarısı (düzey 4) C4989|'*türü*': çakışan tanımları türüne sahip.|
|Derleyici Uyarısı (Düzey 3) C4990|Warbird: *iletisi*|
|Derleyici Uyarısı (Düzey 3) C4991|Warbird: işlev '*işlevi*' koruma düzeyini inlinee üst büyük olduğu için __forceinline içermesinden işaretlenmemiş|
|Derleyici Uyarısı (Düzey 3) C4992|Warbird: işlev '*işlevi*' korunamıyor satır içi derleme içerdiğinden __forceinline içermesinden işaretlenmemiş|
|[Derleyici Uyarısı (düzey 3) C4995](compiler-warning-level-3-c4995.md)|'*işlevi*': ad, kullanım dışı #pragma işaretlendi|
|[Derleyici Uyarısı (düzey 3) C4996](compiler-warning-level-3-c4996.md)|'*açıklama*': *iletisi*|
|Derleyici Uyarısı (düzey 1) C4997|'*sınıfı*': COM arabirimi veya Sahte Arabirimi coclass'ı uygulamıyor|
|Derleyici Uyarısı (düzey 1) C4998|BEKLENTİ başarısız oldu: *Beklenti*(*değeri*)|
|C4999 uyarı derleyici|Lütfen bilinmeyen uyarı Visual C++ Yardım menüsünden teknik destek komut seçin veya daha fazla bilgi için teknik destek Yardım dosyasını açın|
|C5022 uyarı derleyici|'*türü*': belirtilen birden çok taşıma oluşturucuları|
|C5023 uyarı derleyici|'*türü*': belirtilen birden çok taşıma atama işleçleri|
|Derleyici Uyarısı (düzey 4) C5024|'*türü*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma|
|Derleyici Uyarısı (düzey 4) C5025|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma|
|Derleyici Uyarısı (düzey 1 ve düzey 4) C5026|'*türü*': Oluşturucusu silindi olarak örtük olarak tanımlanmıştı taşıma|
|Derleyici Uyarısı (düzey 1 ve düzey 4) C5027|'*türü*': atama işleci silindi olarak örtük olarak tanımlanmıştı taşıma|
|Derleyici Uyarısı (düzey 1) C5028|'*adı*': hizalama önceki bildiriminde belirtilen (*numarası*) tanımı'nda belirtilmedi|
|Derleyici Uyarısı (düzey 4) C5029|kullanılan standart olmayan uzantısı: C++ hizalama öznitelikleri değişkenleri, veri üyeleri ve yalnızca etiket türleri için geçerlidir|
|Derleyici Uyarısı (Düzey 3) C5030|öznitelik '*özniteliği*' tanınmıyor|
|Derleyici Uyarısı (düzey 4) C5031|#pragma warning(pop): farklı bir dosya gönderilen uyarı durumuna pencerelerinin büyük olasılıkla uyuşmazlığı|
|Derleyici Uyarısı (düzey 4) C5032|#pragma warning(push) karşılık gelen hiçbir #pragma warning(pop) ile algılandı|
|Derleyici Uyarısı (düzey 1) C5033|'*depolama sınıfı*' artık desteklenen depolama sınıfı değil|
|C5034 uyarı derleyici|biri iç kullanmak '*iç*' neden işlevi *işlevi* Konuk kodu olarak derlenecek|
|C5035 uyarı derleyici|özelliğini kullanın '*özelliği*' neden işlevi *işlevi* Konuk kodu olarak derlenecek|
|Derleyici Uyarısı (düzey 1) C5036|VarArgs işlev işaretçisi dönüştürme /hybrid:x86arm64 ile derleme yapılırken '*type1*'to'*type2*'|
|Derleyici Uyarısı (hata) C5037|'*üye işlevi*': sınıf şablonu üyesi satır dışı tanımını varsayılan bağımsız değişkenler sahip olamaz|
|[Derleyici Uyarısı (düzey 4) C5038](c5038.md)|veri üyesi '*Üye1*'veri üyesi sonra başlatılacak'*üye2*'|
|Derleyici Uyarısı (düzey 4) C5039|'*işlevi*': - EHc altında extern C işlev işaretçisi veya potansiyel olarak işlevi atma başvuru geçirilen. Bu işlev bir özel durum oluşturursa tanımsız davranış ortaya çıkabilir.|
|Derleyici Uyarısı (Düzey 3) C5040|dinamik özel durum belirtimleri yalnızca C ++ 14 ve daha önceki sürümlerde geçerli; noexcept(FALSE) değerlendirme|
|Derleyici Uyarısı (düzey 1) C5041|'*tanımı*': satır dışı tanım constexpr statik veri üyesi için gerekli değildir ve C ++ 17'de kullanım dışıdır|
|Derleyici Uyarısı (Düzey 3) C5042|'*bildirimi*': blok kapsamında işlev bildirimleri standart C++'da belirtilen 'satır içi' olamaz; 'inline' tanımlayıcısı kaldırın|
|Derleyici Uyarısı (Düzey 2) C5043|'*belirtimi*': özel durum belirtimi önceki bildirimi eşleşmiyor|
|Derleyici Uyarısı (düzey 4) C5044|Komut satırı seçeneğiyle bir bağımsız değişken *seçeneği* bir yola işaret eden '*yolu*' varolmayan|
