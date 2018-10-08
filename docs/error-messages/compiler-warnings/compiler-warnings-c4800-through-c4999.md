---
title: Derleyici uyarılarını C4800 C5999 ile | Microsoft Docs
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
ms.openlocfilehash: deee159c9da6fce9001d010a1a6b1db9b3b1d666
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861427"
---
# <a name="compiler-warnings-c4800-through-c5999"></a>Derleyici uyarılarını C4800 C5999 ile

Belgelerin bu bölümdeki makaleleri bir alt kümesini derleyici tarafından oluşturulan uyarı iletilerini açıklamaktadır.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>Uyarı iletileri

|Uyarı|İleti|
|-------------|-------------|
|[Derleyici Uyarısı (düzey 3) C4800](compiler-warning-level-3-c4800.md)|'*türü*': değer bool 'true' veya 'false' (Performans Uyarısı) zorlama|
|[Derleyici Uyarısı (düzey 1) C4803](compiler-warning-level-1-c4803.md)|'*yöntemi*': yükseltme yönteminde olayın bir farklı depolama sınıfı olan '*olay*'|
|[Derleyici Uyarısı (düzey 1) C4804](compiler-warning-level-1-c4804.md)|'*işlemi*': işlemde ' bool' türü güvensiz kullanımı|
|[Derleyici Uyarısı (düzey 1) C4805](compiler-warning-level-1-c4805.md)|'*işlemi*': Güvenli olmayan karışımı türü '*type1*'ve türü'*type2*' işleminde|
|Derleyici Uyarısı (düzey 1) C4806|'*işlemi*': Güvenli olmayan işlem: değer türü '*type1*'türü için yükseltilen'*type2*' belirtilen Sabitle eşit olamaz|
|Derleyici Uyarısı (düzey 1) C4807|'*işlemi*': Güvenli olmayan karışımı türü '*type1*'ve bit alanı türünün imzalı'*type2*'|
|Derleyici Uyarısı (düzey 1) C4808|Servis talebi '*değer*' 'bool' türünün geçiş koşulu için geçerli bir değer olan|
|Derleyici Uyarısı (düzey 1) C4809|switch ifadesi boş 'default' etiketi var; olası tüm 'case' etiketleri sağlandı|
|Derleyici Uyarısı (düzey 1) C4810|pragma paketi(show) değeri == n|
|Derleyici Uyarısı (düzey 1) C4811|pragma değerini uyumluluk (forscope, show) değeri ==|
|Derleyici Uyarısı (düzey 1) C4812|eski bildirim stili: Lütfen '*new_syntax*' yerine|
|Derleyici Uyarısı (düzey 1) C4813|'*işlevi*': bir arkadaş işlev yerel bir sınıfın önceden bildirilmiş olmalıdır|
|Derleyici Uyarısı (düzey 4) C4816|'*param*': parametre (nesne başvuru ile geçirilmiyorsa) kesilecek bir sıfır boyutlu dizi içeriyor|
|Derleyici Uyarısı (düzey 1) C4817|'*üye*': geçersiz kullanımı '.' Bu üye; erişmek için derleyici '->' ile değiştirildi|
|[Derleyici Uyarısı (düzey 1) C4819](compiler-warning-level-1-c4819.md)|Dosya (sayı) geçerli kod sayfasında temsil edilemeyen bir karakter içeriyor. Dosyayı veri kaybını önlemek için Unicode biçiminde kaydedin|
|[Derleyici Uyarısı (düzey 4) C4820](compiler-warning-level-4-c4820.md)|'*bayt*'bayt doldurma eklenen sonra yapı'*member_name*'|
|[Derleyici Uyarısı (düzey 1) C4821](compiler-warning-level-1-c4821.md)|Unicode kodlama türü belirlenemiyor, Lütfen dosyayı (BOM) imzasıyla kaydedin|
|Derleyici Uyarısı (düzey 1) C4822|'üye işlev': yerel sınıf üyesi işlevinde bir gövde yok|
|[Derleyici Uyarısı (düzey 3) C4823](compiler-warning-level-3-c4823.md)|'*işlevi*': kullanır ancak sabitleme işaretçileri geriye doğru izlenen semantik etkin değil. / Eha kullanmayı düşünün|
|Derleyici Uyarısı (Düzey 2) C4826|Dönüştürme işlemi '*type1*'to'*type2*' işaret genişletilmiş. Bu, beklenmeyen çalışma zamanı davranışına neden olabilir.|
|Derleyici Uyarısı (Düzey 3) C4827|0 paramterleri bir genel 'ToString' yöntemi sanal olarak işaretlenmesi gerekir ve geçersiz kılma|
|[Derleyici Uyarısı (düzey 1) C4829](compiler-warning-level-1-c4829.md)|Büyük olasılıkla yanlış parametreler ana işlev. Göz önünde bulundurun ' int main (Platform::Array\<Platform::String ^ > ^ argv)'|
|[Derleyici Uyarısı (düzey 1) C4835](compiler-warning-level-1-c4835.md)|'*değişkeni*': dışarı aktarılan veriler için Başlatıcı, önce yönetilen kod ana bilgisayar derlemesinde yürütülene kadar çalıştırılmayacak|
|Derleyici Uyarısı (düzey 4) C4837|Üçlü harf algılandı: '?? *karakter*'yerine'*karakter*'|
|[Derleyici Uyarısı (düzey 1) C4838](compiler-warning-level-1-c4838.md)|dönüştürme işlemi '*type_1*'to'*type_2*' bir daraltma dönüşümü gerektirir|
|[Derleyici Uyarısı (Düzey 3) C4839](compiler-warning-level-3-c4839.md)|sınıfının standart dışı kullanımı*türü*' bir bağımsız değişken içeren işlev bağımsız değişkeni olarak|
|[Derleyici Uyarısı (düzey 4) C4840](compiler-warning-level-4-c4840.md)|sınıfının taşınabilir olmayan kullanımı*türü*' bir bağımsız değişken içeren işlev bağımsız değişkeni olarak|
|Derleyici Uyarısı (düzey 4) C4841|Standart olmayan uzantı kullanıldı: kullanılan offsetof içinde bileşik üye göstergesi|
|Derleyici Uyarısı (düzey 4) C4842|birden fazla devralma kullanılarak bir türe uygulanan'offsetof ' sonucunun derleyici yayınları arasında tutarlı olması garanti edilmez|
|Derleyici Uyarısı C4843|'*type1*': dizi veya işlev türüne yapılan başvurunun özel durum işleyicisi erişilemiyor, kullanın '*type2*' yerine|
|Derleyici Uyarısı C4844|' export module *module_name*;' artık bir modül arabirimi bildirmek için tercih edilen sözdizimi şöyledir|
|[Derleyici Uyarısı (düzey 4) C4866](c4866.md)| Derleyici, soldan sağa Değerlendirme sırasını çağrısı değil zorlayabileceği *operator_name*|
|[Derleyici Uyarısı (hata) C4867](compiler-warning-c4867.md)|'*işlevi*': işlev çağrısında bağımsız değişken listesi eksik; bu değer '*çağrı*' bir üyeye işaretçi oluşturmak için|
|[Derleyici Uyarısı (düzey 4) C4868](compiler-warning-c4868.md)|'_dosya_(*line_number*)' derleyici küme ayracıyla belirtilen başlatma listesi soldan sağa Değerlendirme sırasını zorla|
|Derleyici Uyarısı (Düzey 2) C4872|concurrency::parallel_for_each için çağrı grafı derlenirken desteklenemeyen sıfıra bölme noktasına kayan: '*konumu*'|
|Derleyici Uyarısı (düzey 1) C4880|gelen atama ' const *type_1*'to'*type_2*': bir işaretçi veya başvuru sabitliği hemen atama amp sınırlı işlevde tanımlanmayan davranışta sonuçlanabilir|
|Derleyici Uyarısı (düzey 4) C4881|Oluşturucu ve/veya yok edici tile_static değişkeni için çağrılmayacak '*değişkeni*'|
|Derleyici Uyarısı (düzey 1) C4882|non-const çağrı işleçleri olan functorları concurrency::parallel_for_each içine geçirmek kullanım dışıdır|
|Derleyici Uyarısı C4900|Arasında IL uyuşmazlığı '*tool1*'version'*version1*'ve'*tool2*'version'*version2*'|
|[Derleyici Uyarısı (düzey 1) C4905](compiler-warning-level-1-c4905.md)|geniş düz dize 'LPSTR' değerine atandı|
|[Derleyici Uyarısı (düzey 1) C4906](compiler-warning-level-1-c4906.md)|düz dize 'LPWSTR' değerine atandı|
|Derleyici Uyarısı (düzey 1) C4910|'\<tanımlayıcısı >: '__declspec(dllexport)' ve 'extern' açık bir örnek oluşturmada uyumsuz|
|Derleyici Uyarısı (düzey 1) C4912|'*özniteliği*': özniteliği bir iç içe geçmiş UDT'de davranışı tanımlı değil|
|Derleyici Uyarısı (düzey 4) C4913|Kullanıcı tanımlı ikili işleç ',' var ancak hiçbir aşırı yüklemesi dönüştüremedi tüm işlenenler, varsayılan yerleşik ikili operatör ',' kullanılan|
|Derleyici Uyarısı (düzey 1) C4916|dispid değerine sahip olmak için '*açıklama*': arabirim tarafından sunulan gerekir|
|[Derleyici Uyarısı (düzey 1) C4917](compiler-warning-level-1-c4917.md)|'*bildirimci*': bir GUID yalnızca bir sınıf, arabirim veya ad alanı ile ilişkilendirilebilir.|
|Derleyici Uyarısı (düzey 4) C4918|'*karakter*': pragram iyileştirme listesinde geçersiz karakter|
|Derleyici Uyarısı (düzey 1) C4920|Enum sabit listesi üyesi member_1 numaralandırma sabit listesi member_2 zaten görüldü value_1 = value_2 =|
|Derleyici Uyarısı (Düzey 3) C4921|'*açıklama*': öznitelik değeri '*özniteliği*' birden çok kez belirtilmesi|
|Derleyici Uyarısı (düzey 1) C4925|'*yöntemi*': dispinterface yöntemi betikten çağrılamaz|
|Derleyici Uyarısı (düzey 1) C4926|'*tanımlayıcı*': simge zaten tanımlandı: öznitelikler yoksayıldı|
|[Derleyici Uyarısı (düzey 1) C4927](compiler-warning-level-1-c4927.md)|hatalı dönüştürme; birden fazla kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[Derleyici Uyarısı (düzey 1) C4928](compiler-warning-level-1-c4928.md)|hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı|
|[Derleyici Uyarısı (düzey 1) C4929](compiler-warning-level-1-c4929.md)|'*dosya*': tür kitaplığı bir birleşim içeriyor; 'embedded_idl' niteleyicisi yoksayılıyor|
|[Derleyici Uyarısı (düzey 1) C4930](compiler-warning-level-1-c4930.md)|'*prototip*': prototipli işlev çağrılmadı (değişken bir tanım hedeflenen oldu mu?)|
|[Derleyici Uyarısı (düzey 4) C4931](compiler-warning-level-4-c4931.md)|tür kitaplığının sayı bit işaretçiler için oluşturulduğunu varsayıyoruz|
|Derleyici Uyarısı (düzey 4) C4932|__tanımlayıcı (*tanımlayıcı*) ve \__tanımlayıcı (*tanımlayıcı*) ayırt edilemiyor|
|Derleyici Uyarısı (düzey 1) C4934|'__delegate(multicast)' kullanım dışı bırakılmıştır, Kullan '\__delegate' yerine|
|Derleyici Uyarısı (düzey 1) C4935|derleme erişim belirticisi değiştiren gelen '*erişim*'|
|Derleyici Uyarısı (düzey 1, hata) C4936|Bu __declspec yalnızca/CLR veya/CLR ile derlendiğinde desteklenir: Saf|
|Derleyici Uyarısı (düzey 4) C4937|'*text1*'ve'*text2*'için bağımsız değişkenler olarak ayırt edilemiyor'*yönergesi*'|
|Derleyici Uyarısı (düzey 4) C4938|'*var*': kayan nokta azaltma değişkeni, / FP altında tutarsız sonuçlara neden olabilir: strict veya #pragma fenv_access|
|Derleyici Uyarısı C4939|#pragma vtordisp kullanım dışı ve Visual C++'ın gelecek sürümde kaldırılacak.|
|Derleyici Uyarısı (düzey 1) C4944|'*sembol*': değerinden simge alınamıyor '*assembly1*': farklı*sembol*' geçerli kapsamda zaten var.|
|[Derleyici Uyarısı (düzey 1) C4945](compiler-warning-level-1-c4945.md)|'*sembol*': değerinden simge alınamıyor '*assembly1*': farklı*sembol*'başka bir derleme zaten alınmış'*assembly2* '|
|[Derleyici Uyarısı (düzey 1) C4946](compiler-warning-level-1-c4946.md)|reinterpret_cast ilgili sınıflar arasında kullanıldı: '*class1*'ve'*class2*'|
|Derleyici Uyarısı (düzey 1) C4947|'*type_or_member*': eski olarak işaretlendi|
|[Derleyici Uyarısı (düzey 2) C4948](compiler-warning-level-2-c4948.md)|dönüş türü '*erişimci*' karşılık gelen ayarlayıcının son parametre türüyle eşleşmiyor|
|[Derleyici Uyarısı (düzey 1 ve düzey 4) C4949](compiler-warning-level-1-and-level-4-c4949.md)|'managed' ve 'unmanaged' pragmaları yalnızca ile derlendikleri zaman anlamlıdır ' / clr [: option]'|
|Derleyici Uyarısı (düzey 1, hata) C4950|'*type_or_member*': eski olarak işaretlendi|
|Derleyici Uyarısı (düzey 1) C4951|'*işlevi*' profili beri işlevi profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir|
|Derleyici Uyarısı (düzey 1) C4952|'*işlevi*': program veritabanında profil verileri bulunamadı '*pgd_file*'|
|Derleyici Uyarısı (düzey 1) C4953|Alınanın '*işlevi*' profili bu yana profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir|
|Derleyici Uyarısı C4954|'*işlevi*': oluşturulmamış (__int64 geçiş ifadesi içeriyor)|
|Derleyici Uyarısı C4955|'*import2*': alma yoksayıldı; zaten içeri aktarılan '*import1*'|
|Derleyici Uyarısı (düzey 1, hata) C4956|'*türü*': Bu tür doğrulanabilir değil|
|Derleyici Uyarısı (düzey 1, hata) C4957|'*atama*': açık tür dönüştürme gelen '*cast_from*'to'*cast_to*' doğrulanabilir değil|
|Derleyici Uyarısı (düzey 1, hata) C4958|'*işlemi*': işaretçi aritmetik doğrulanabilir değil|
|Derleyici Uyarısı (düzey 1, hata) C4959|yönetilmeyen tür tanımlanamaz '*türü*' / CLR: safe, üyelerine erişilmesi doğrulanamayan bir koda neden olduğu|
|Derleyici Uyarısı (düzey 4) C4960|'*işlevi*' profili çok büyük|
|Derleyici Uyarısı (düzey 1) C4961|Hiç profil verisi birleştirilmiş '.pgd dosyası ', profil temelli iyileştirmeler devre dışı bırakıldı|
|Derleyici Uyarısı (düzey 4) C4962|'*işlevi*': iyileştirmeler profil verilerinin tutarsız olmasına yol açtığı için devre dışı profil temelli iyileştirmeler|
|Derleyici Uyarısı (düzey 1) C4963|'*açıklama*': Profil verileri bulunamadı; işaretlenmiş yapımda farklı derleyici seçenekleri kullanılmış|
|[Derleyici Uyarısı (düzey 1) C4964](compiler-warning-level-1-c4964.md)|İyileştirme seçeneği belirtilmedi; profil bilgileri toplanmayacak değil|
|[Derleyici Uyarısı (düzey 1) C4965](compiler-warning-level-1-c4965.md)|örtük 0 tamsayı kutusunu; nullptr veya açık tür dönüştürme kullanın|
|Derleyici Uyarısı (düzey 1) C4966|'*işlevi*' açıklama yoksayıldı, desteklenmeyen segment adı olan __code_seg ek açıklaması var|
|Derleyici Uyarısı C4970|temsilci oluşturucusu: hedef nesne yoksayıldı beri '*türü*' statik|
|Derleyici Uyarısı (düzey 1) C4971|Bağımsız değişken sırası: \<hedef nesne >, \<hedef işlev > temsilci Oluşturucu kullanım dışı bırakılmıştır, kullanın \<hedef işlev >, \<hedef nesne = "" >|
|Derleyici Uyarısı (düzey 1, hata) C4972|Doğrudan değiştirme ya da açma işleminin sonucu lvalue olarak değerlendirmek doğrulanamaz|
|Derleyici Uyarısı (düzey 1) C4973|'*sembol*': kullanım dışı olarak işaretlendi|
|Derleyici Uyarısı (düzey 1) C4974|'*sembol*': kullanım dışı olarak işaretlendi|
|Derleyici Uyarısı (Düzey 3) C4981|Warbird: işlev '*işlevi*' __forceinline olarak değil, özel durum anlamsalları içerdiği için satır içine alınmış işaretlenmiş.|
|Derleyici Uyarısı (Düzey 3) C4985|Sembol adı ': öznitelikler önceki bildirimde yok.|
|[Derleyici Uyarısı C4986](compiler-warning-c4986.md)|'*bildirimi*': özel durum belirtimi, önceki bildirimle eşleşmiyor|
|Derleyici Uyarısı (düzey 4) C4987|standart olmayan uzantı kullanıldı: 'throw (...)'|
|Derleyici Uyarısı (düzey 4) C4988|'*değişkeni*': değişken sınıf/işlev kapsamının dışında bildirildi|
|Derleyici Uyarısı (düzey 4) C4989|'*türü*': türde çakışan tanımlar.|
|Derleyici Uyarısı (Düzey 3) C4990|Warbird: *iletisi*|
|Derleyici Uyarısı (Düzey 3) C4991|Warbird: işlev '*işlevi*' alınanın koruma düzeyi üst büyük olduğundan __forceinline olarak satır içine alınmış işaretlenen|
|Derleyici Uyarısı (Düzey 3) C4992|Warbird: işlev '*işlevi*' Korunamayan satır içi bütünleştirilmiş içerdiğinden __forceinline olarak satır içine alınmış işaretlenen|
|[Derleyici Uyarısı (düzey 3) C4995](compiler-warning-level-3-c4995.md)|'*işlevi*': ad kullanım dışı #pragma olarak işaretlendi|
|[Derleyici Uyarısı (düzey 3) C4996](compiler-warning-level-3-c4996.md)|'*açıklama*': *iletisi*|
|Derleyici Uyarısı (düzey 1) C4997|'*sınıfı*': coclass COM arabirimi veya sahte arabirim uygulamıyor|
|Derleyici Uyarısı (düzey 1) C4998|BEKLENTİ başarısız oldu: *beklentisi*(*değer*)|
|Derleyici Uyarısı C4999|Bilinmeyen uyarısı Lütfen Visual C++ Yardım menüsünde teknik destek komutunu seçin veya daha fazla bilgi için teknik destek Yardım dosyasını açın|
|Derleyici Uyarısı C5022|'*türü*': belirtilen birden fazla taşıma oluşturucuları|
|Derleyici Uyarısı C5023|'*türü*': belirtilen birden fazla taşıma atama işleçleri|
|Derleyici Uyarısı (düzey 4) C5024|'*türü*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı|
|Derleyici Uyarısı (düzey 4) C5025|'*türü*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı|
|Derleyici Uyarısı (düzey 1 ve düzey 4) C5026|'*türü*': taşıma Oluşturucusu örtük bir şekilde silindi olarak tanımlandı|
|Derleyici Uyarısı (düzey 1 ve düzey 4) C5027|'*türü*': taşıma atama işleci örtük bir şekilde silindi olarak tanımlandı|
|Derleyici Uyarısı (düzey 1) C5028|'*adı*': hizalama önceki bildirimde belirtilen (*numarası*) belirtilmemiş|
|Derleyici Uyarısı (düzey 4) C5029|Standart olmayan uzantı kullanıldı: C++ hizalama öznitelikleri değişkenlere, veri üyelerine ve etiket türlerine uygulanır|
|Derleyici Uyarısı (Düzey 3) C5030|öznitelik '*özniteliği*' tanınmıyor|
|Derleyici Uyarısı (düzey 4) C5031|#pragma warning(pop): olası uyuşmazlık, farklı bir dosyada atılan uyarı durumu geri çağrılıyor|
|Derleyici Uyarısı (düzey 4) C5032|hiçbir karşılık gelen #pragma warning(pop) olmayan #pragma algılandı|
|Derleyici Uyarısı (düzey 1) C5033|'*depolama sınıfı*' artık desteklenen bir depolama sınıfı değil|
|Derleyici Uyarısı C5034|İç Kullan '*iç*' neden işlevi *işlevi* Konuk kodu olarak derlenmesine neden|
|Derleyici Uyarısı C5035|özelliğini '*özellik*' neden işlevi *işlevi* Konuk kodu olarak derlenmesine neden|
|Derleyici Uyarısı (düzey 1) C5036|VarArgs işlev işaretçisi dönüştürme x86arm64 ile derleme yapılırken '*type1*'to'*type2*'|
|Derleyici Uyarısı (hata) C5037|'*üye işlevi*': bir sınıf şablonunun üyesi bir satır dışı tanımı varsayılan bağımsız değişkenlere sahip olamaz|
|[Derleyici Uyarısı (düzey 4) C5038](c5038.md)|veri üyesi '*Üye1*'veri üyesi sonra başlatılacak'*üye2*'|
|Derleyici Uyarısı (düzey 4) C5039|'*işlevi*': - EHc altında extern C işlevine işaretçi veya başvuru için büyük olasılıkla işlev özel durum atma geçirildi. Bu işlev bir özel durum oluşturursa tanımsız davranış ortaya çıkabilir.|
|Derleyici Uyarısı (Düzey 3) C5040|dinamik özel durum belirtimleri yalnızca C ++ 14 ve daha önceki sürümlerde geçerlidir; noexcept(FALSE) değerlendirme|
|Derleyici Uyarısı (düzey 1) C5041|'*tanımı*': constexpr statik veri üyesi için satır dışı tanımı gerekli değildir ve C ++ 17'de kullanım dışıdır|
|Derleyici Uyarısı (Düzey 3) C5042|'*bildirimi*': blok kapsamındaki işlev bildirimleri, standart C++'da belirtilen 'inline' olamaz; 'inline' tanımlayıcısını kaldırın|
|Derleyici Uyarısı (Düzey 2) C5043|'*belirtimi*': özel durum belirtimi, önceki bildirimle eşleşmiyor|
|Derleyici Uyarısı (düzey 4) C5044|Komut satırı seçeneği bir bağımsız değişken *seçeneği* yolunu işaret '*yolu*' mevcut olmayan|
|[C5045 uyarı derleyici](c5045.md)|Derleyici/qspectre anahtarı Bellek Yükü belirtilen için Spectre risk azaltma ekler|
