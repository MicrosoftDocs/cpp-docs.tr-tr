---
title: C999 ile C1999 arasındaki önemli derleyici hataları
ms.date: 04/21/2019
f1_keywords:
- C1034
- C1036
- C1041
- C1048
- C1049
- C1063
- C1069
- C1101
- C1102
- C1105
- C1110
- C1111
- C1112
- C1114
- C1193
- C1195
- C1300
- C1301
- C1302
- C1306
- C1384
- C1451
- C1505
- C1901
helpviewer_keywords:
- C1034
- C1036
- C1041
- C1048
- C1049
- C1063
- C1069
- C1101
- C1102
- C1105
- C1110
- C1111
- C1112
- C1114
- C1193
- C1195
- C1300
- C1301
- C1302
- C1306
- C1384
- C1451
- C1505
- C1901
ms.assetid: 6c8df109-7594-48ed-987a-97d9fe2b04af
ms.openlocfilehash: 5ffa1a2633877c8a16eb424f1ddc100bfd6142b8
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857389"
---
# <a name="compiler-fatal-errors-c999-through-c1999"></a>C999 ile C1999 arasındaki önemli derleyici hataları

Belgelerin bu bölümdeki makaleleri bir alt kümesini Microsoft C tarafından oluşturulan hata iletilerini açıklayın /C++ derleyici.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Hata iletileri

|Hata|`Message`|
|-----------|-------------|
|[Önemli hata C999](../../error-messages/compiler-errors-1/fatal-error-c999.md)|Bilinmeyen ileti Lütfen Visual C++ Yardım menüsünde teknik destek komutunu seçin veya daha fazla bilgi için teknik destek Yardım dosyasını açın|
|[Önemli hata C1001](../../error-messages/compiler-errors-1/fatal-error-c1001.md)|Derleyicide bir iç hata oluştu.<br /> (derleyici dosyası '*dosya*', satır *numarası*)<br /> Basitleştirmeyi veya yukarıda listelenen konumların yakınındaki programı değiştirmeyi deneyin. Bu sorunu geçici olarak çözmek için. Lütfen Visual C++ Yardım menüsünde teknik destek komutunu seçin veya daha fazla bilgi için teknik destek Yardım dosyasını açın|
|[Önemli hata C1002](../../error-messages/compiler-errors-1/fatal-error-c1002.md)|2. geçiş yığın tükendi derleyicisidir|
|[Önemli hata C1003](../../error-messages/compiler-errors-1/fatal-error-c1003.md)|hata sayısı *numarası*; derleme durduruluyor|
|[Önemli hata C1004](../../error-messages/compiler-errors-1/fatal-error-c1004.md)|Beklenmeyen bitiş-dosya bulundu|
|[Önemli hata C1005](../../error-messages/compiler-errors-1/fatal-error-c1005.md)|dize için arabellek çok büyük|
|[Önemli hata C1007](../../error-messages/compiler-errors-1/fatal-error-c1007.md)|Tanınmayan bayrak '*dize*'in'*seçeneği*'|
|[Önemli hata C1008](../../error-messages/compiler-errors-1/fatal-error-c1008.md)|Giriş dosyası belirtilmedi|
|[Önemli hata C1009](../../error-messages/compiler-errors-1/fatal-error-c1009.md)|Derleyici sınırı: makrolar çok derin iç içe|
|[Önemli hata C1010](../../error-messages/compiler-errors-1/fatal-error-c1010.md)|Beklenmeyen için önceden derlenmiş üst bilgi arayan sırasında dosya sonu. Eklemeyi mi unuttunuz ' #include \< *dosya*>', kaynak için?|
|[Önemli hata C1012](fatal-error-c1012.md)|eşleşmeyen parantez: eksik '*karakter*"|
|[Önemli hata C1013](fatal-error-c1013.md)|Derleyici sınırı: çok fazla açık parantez var|
|[Önemli hata C1014](fatal-error-c1014.md)|çok fazla sayıda ekleme dosyası: derinlik = *numarası*|
|[Önemli hata C1016](fatal-error-c1016.md)|#ifdef / #ifndef bir tanımlayıcı bekleniyor|
|[Önemli hata C1017](../../error-messages/compiler-errors-1/fatal-error-c1017.md)|Geçersiz tamsayı sabit ifadesi|
|[Önemli hata C1018](fatal-error-c1018.md)|Beklenmeyen #elif|
|[Önemli hata C1019](fatal-error-c1019.md)|Beklenmeyen #else|
|[Önemli hata C1020](fatal-error-c1020.md)|Beklenmeyen #endif|
|[Önemli hata C1021](fatal-error-c1021.md)|Geçersiz önişlemci komutu '*dize*'|
|[Önemli hata C1022](fatal-error-c1022.md)|#endif bekleniyor|
|[Önemli hata C1023](fatal-error-c1023.md)|'*dosya*': beklenmeyen pch hatası, pch'yi yeniden oluşturmayı deneyin deneyin|
|[Önemli hata C1026](../../error-messages/compiler-errors-1/fatal-error-c1026.md)|Ayrıştırıcı yığını taştı, program çok karmaşık|
|[Önemli hata C1033](../../error-messages/compiler-errors-1/fatal-error-c1033.md)|Program veritabanı açılamıyor. '*dosya*'|
|Önemli hata C1034|*Dosya*: hiçbir ekleme yolu ayarlanmadı|
|[Önemli hata C1035](fatal-error-c1035.md)|ifade çok karmaşık; ifadesini Basitleştir|
|Önemli hata C1036|önceki program veritabanı biçiminin üzerine olamaz, Sil '*dosya*' ve yeniden derleyin|
|[Önemli hata C1037](fatal-error-c1037.md)|nesne dosyası açılamıyor '*dosya*'|
|[Önemli hata C1038](fatal-error-c1038.md)|Derleyici sınırı: '*işlevi*': denetim akışı durumu çok karmaşık; işlevi basitleştirin|
|Önemli hata C1041|Program veritabanı açılamıyor. '*dosya*' if birden çok CL. EXE aynı yazın. PDB dosyası, lütfen /FS kullanın|
|[Önemli hata C1045](fatal-error-c1045.md)|Derleyici sınırı: bağlantı belirtimleri çok derin iç içe|
|[Önemli hata C1046](../../error-messages/compiler-errors-1/fatal-error-c1046.md)|Derleyici sınırı: *yapısı* çok derin iç içe geçmiş|
|[Önemli hata C1047](fatal-error-c1047.md)|Nesne veya kitaplık dosyası '*dosya*' diğer nesnelere; yeniden eski nesneleri ve kitaplıkları daha eski bir derleyici ile oluşturulmuş|
|Önemli hata C1048|Bilinmeyen seçenek '*dize*'in'*seçeneği*'|
|Önemli hata C1049|Geçersiz sayısal bağımsız değişken '*değer*'|
|[Önemli hata C1051](../../error-messages/compiler-errors-1/fatal-error-c1051.md)|Program veritabanı dosyası, '*dosya*', silin ve yeniden derleyin geçersiz bir biçime sahip|
|[Önemli hata C1052](fatal-error-c1052.md)|Program veritabanı dosyası, '*filename*', / Debug: fastlink ile; bağlayıcı tarafından oluşturulan derleyici olamaz tür PDB dosyalarını güncelleştiremez; Lütfen silin veya /Fd farklı bir PDB dosya adı belirtmek için kullanın|
|[Önemli hata C1053](fatal-error-c1053.md)|'*işlevi*': işlev çok büyük|
|[Önemli hata C1054](../../error-messages/compiler-errors-1/fatal-error-c1054.md)|Derleyici sınırı: başlatıcılar çok derin iç içe|
|[Önemli hata C1055](../../error-messages/compiler-errors-1/fatal-error-c1055.md)|Derleyici sınırı: anahtar kalmadı|
|[Önemli hata C1057](../../error-messages/compiler-errors-1/fatal-error-c1057.md)|beklenmeyen dosya sonu makro genişletme içinde|
|[Önemli hata C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)|Derleyicinin yığın alanı yetersiz olduğu|
|[Önemli hata C1061](../../error-messages/compiler-errors-1/fatal-error-c1061.md)|Derleyici sınırı: bloklar çok derin iç içe|
|Önemli hata C1063|Derleyici sınırı: derleyicide yığın taşması|
|[Önemli hata C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md)|Derleyici sınırı: belirteç iç arabelleği taşırdı|
|[Önemli hata C1065](../../error-messages/compiler-errors-1/fatal-error-c1065.md)|Derleyici sınırı: Etiket kalmadı|
|[Önemli hata C1067](../../error-messages/compiler-errors-1/fatal-error-c1067.md)|Derleyici sınırı: Bir tür kaydının boyutu 64K sınırı aşıldı|
|[Önemli hata C1068](fatal-error-c1068.md)|Dosya açılamıyor '*dosya*'|
|Önemli hata C1069|derleyici komut satırı okunamıyor|
|[Önemli hata C1070](fatal-error-c1070.md)|eşleşmeyen #if / #endif pair dosyasında '*dosya*'|
|[Önemli hata C1071](../../error-messages/compiler-errors-1/fatal-error-c1071.md)|Beklenmeyen açıklamada dosya sonu bulundu|
|[Önemli hata C1073](../../error-messages/compiler-errors-1/fatal-error-c1073.md)|Artımlı derleme içeren bir iç hata (derleyici dosyası '*dosya*', satır *numarası*)|
|[Önemli hata C1074](fatal-error-c1074.md)|'IDB', PDB dosyası için geçersiz bir uzantı: *dosyası*|
|[Önemli hata C1075](../../error-messages/compiler-errors-1/fatal-error-c1075.md)|Sol *belirteci* dosyasının sonunda eşleşmeyen oluştu|
|[Önemli hata C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)|Derleyici sınırı: iç yığın sınırı aşıldı; daha yüksek bir sınır belirtmek için /ZM kullanın|
|[Önemli hata C1077](fatal-error-c1077.md)|Derleyici sınırı: olamaz birden fazla *numarası* komut satırı seçenekleri|
|[Önemli hata C1079](../../error-messages/compiler-errors-1/fatal-error-c1079.md)|Derleyici sınırı: PCH dosyası boyut sınırı aşıldı|
|[Önemli hata C1080](../../error-messages/compiler-errors-1/fatal-error-c1080.md)|Derleyici sınırı: komut satırı seçeneği aşıldı sınırının *numarası* karakter|
|[Önemli hata C1081](../../error-messages/compiler-errors-1/fatal-error-c1081.md)|'*dosya*': dosya adı çok uzun|
|[Önemli hata C1082](fatal-error-c1082.md)|kapatamazsınız *türü* dosya: '*dosya*': *iletisi*|
|[Önemli hata C1083](../../error-messages/compiler-errors-1/fatal-error-c1083.md)|açılamıyor *türü* dosya: '*dosya*': *iletisi*|
|[Önemli hata C1084](../../error-messages/compiler-errors-1/fatal-error-c1084.md)|okunamıyor *türü* dosya: '*dosya*': *iletisi*|
|[Önemli hata C1085](../../error-messages/compiler-errors-1/fatal-error-c1085.md)|nelze zapisovat do *türü* dosya: '*dosya*': *iletisi*|
|[Önemli hata C1086](fatal-error-c1086.md)|nelze vyhledat danou pozici *türü* dosya: '*dosya*': *iletisi*|
|[Önemli hata C1087](fatal-error-c1087.md)|nejde *türü* dosya: '*dosya*': *iletisi*|
|[Önemli hata C1088](fatal-error-c1088.md)|temizleyemiyor *türü* dosya: '*dosya*': *iletisi*|
|[Önemli hata C1089](fatal-error-c1089.md)|kesilemiyor *türü* dosya: '*dosya*': *iletisi*|
|Önemli hata C1090|PDB API çağrısı başarısız oldu, hata kodu '*kod*': '*ileti*'|
|[Önemli hata C1091](fatal-error-c1091.md)|Derleyici sınırı: dize aşıyor *numarası* bayt cinsinden uzunluğu|
|[Önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)|Düzenle ve devam et değişiklikleri veri türlerini desteklemez; gerekli derleme|
|[Önemli hata C1093](../../error-messages/compiler-errors-1/fatal-error-c1093.md)|API çağrısı '*işlevi*'başarısız'*HRESULT*': '*açıklama*'|
|[Önemli hata C1094](../../error-messages/compiler-errors-1/fatal-error-c1094.md)|'-Zm*numarası*': komut satırı seçeneği ön derlenmiş üstbilgiyi oluşturmak için kullanılan değerle tutarsız ('-Zm*sayı*')|
|[Önemli hata C1098](fatal-error-c1098.md)|Düzenle ve devam et altyapısında sürüm uyuşmazlığı|
|[Önemli hata C1099](fatal-error-c1099.md)|Düzenle ve devam et altyapısı derlemeyi sonlandırıyor|
|[Önemli hata C1100](fatal-error-c1100.md)|OLE başlatılamıyor: *hata*|
|Önemli hata C1101|özniteliği için işleyici oluşturulamıyor '*tanımlayıcı*'|
|Önemli hata C1102|başlatılamıyor: *hata*|
|[Önemli hata C1103](fatal-error-c1103.md)|önemli hata program kimliği içeri aktarılırken: '*ileti*'|
|[Önemli hata C1104](fatal-error-c1104.md)|Kitaplık kimliği içeri aktarılırken önemli hata: '*ileti*'|
|Önemli hata C1105|*İleti*: *hata*|
|[Önemli hata C1107](../../error-messages/compiler-errors-1/fatal-error-c1107.md)|bütünleştirilmiş kod bulunamadı '*derleme*': Lütfen /AI kullanarak bütünleştirilmiş kod arama yolunu belirtin veya LIBPATH ortam değişkenini ayarlayarak|
|[Önemli hata C1108](fatal-error-c1108.md)|DLL bulunamadı: '*dosya*'|
|[Önemli hata C1109](fatal-error-c1109.md)|bulunamadı '*sembol*'DLL' ın*dosya*'|
|Önemli hata C1110|çok fazla iç içe geçmiş şablon/genel tanımları|
|Önemli hata C1111|çok fazla sayıda şablon/genel parametre|
|Önemli hata C1112|Derleyici sınırı: `'number`' fazla makro bağımsız değişkeni, yalnızca *numarası* izin|
|[Önemli hata C1113](../../error-messages/compiler-errors-1/fatal-error-c1113.md)|#using başarısız oldu '*dosya*'|
|Önemli hata C1114|'*dosya*': WinRT desteklemiyor # yönetilen derlemenin using|
|[Önemli hata C1120](../../error-messages/compiler-errors-1/fatal-error-c1120.md)|GetProcAddress için başarısız oldu: Çağrı '*işlevi*'|
|[Önemli hata C1121](../../error-messages/compiler-errors-1/fatal-error-c1121.md)|CryptoAPI'ye kopyalama başarısız oldu|
|[Önemli hata C1126](../../error-messages/compiler-errors-1/fatal-error-c1126.md)|Otomatik aşması *boyutu*|
|[Önemli hata C1128](../../error-messages/compiler-errors-1/fatal-error-c1128.md)|bölüm sayısı nesne dosyası biçimi sınırını aştı: / bigobj ile derleyin|
|[Önemli hata C1189](../../error-messages/compiler-errors-1/fatal-error-c1189.md)|#error: *iletisi*|
|[Önemli hata C1190](fatal-error-c1190.md)|Yönetilen hedeflenen kod gerektiren bir ' / clr' seçeneği|
|[Önemli hata C1191](../../error-messages/compiler-errors-1/fatal-error-c1191.md)|'*dosya*' yalnızca küresel kapsamda içeri|
|[Önemli hata C1192](../../error-messages/compiler-errors-1/fatal-error-c1192.md)|#using başarısız oldu '*dosya*'|
|Önemli hata C1193|bir hata beklenen *dosya*(*satırı*) ulaşılmadı|
|Önemli hata C1195|/Yu ve /Yc aynı komut satırında kullanılması/CLR seçeneğiyle uyumsuzdur|
|[Önemli hata C1196](fatal-error-c1196.md)|'*tanımlayıcı*': tür kitaplığındaki tanımlayıcı bulunamadı '*typelib*' geçerli bir C++ tanımlayıcısı değil|
|[Önemli hata C1197](../../error-messages/compiler-errors-1/fatal-error-c1197.md)|başvuruda bulunamaz. '*dosya*'program zaten başvurmuş gibi'*dosya*'|
|[Önemli hata C1201](fatal-error-c1201.md)|sınıf şablonu tanımındaki sözdizimi hatasından sonra devam edilemiyor|
|[Önemli hata C1202](fatal-error-c1202.md)|özyinelemeli tür veya işlev bağımlılığı bağlamı çok karmaşık|
|[Önemli hata C1205](fatal-error-c1205.md)|Genel türler yüklü olan çalışma zamanı sürümü tarafından desteklenmiyor|
|[Önemli hata C1206](fatal-error-c1206.md)|Appdomain başına veriler yüklü olan çalışma zamanı sürümü tarafından desteklenmiyor|
|[Önemli hata C1207](fatal-error-c1207.md)|Yönetilen şablonlar yüklü olan çalışma zamanı sürümü tarafından desteklenmiyor|
|[Önemli hata C1208](fatal-error-c1208.md)|Yığında başvuru sınıfları ayırma yüklü olan çalışma zamanı sürümü tarafından desteklenmiyor|
|[Önemli hata C1209](fatal-error-c1209.md)|Arkadaş derlemeler yüklü olan çalışma zamanı sürümü tarafından desteklenmiyor|
|[Önemli hata C1210](fatal-error-c1210.md)|/ CLR: pure ve/CLR: safe yüklü olan çalışma zamanı sürümü tarafından desteklenmiyor|
|[Önemli hata C1211](fatal-error-c1211.md)|TypeForwardedTo özel özniteliği yüklü olan çalışma zamanı sürümü tarafından desteklenmiyor|
|Önemli hata C1300|Program veritabanına erişme hatası *dosya* (*ileti*)|
|Önemli hata C1301|Program veritabanına erişme hatası *dosya*, geçersiz biçim, lütfen silin ve yeniden oluşturun|
|Önemli hata C1302|hiç profil verisi modülü için '*Modülü*'profil veritabanındaki'*dosya*'|
|[Önemli hata C1305](../../error-messages/compiler-errors-1/fatal-error-c1305.md)|profil veritabanı '*dosya*' için farklı bir mimari|
|Önemli hata C1306|Son profil verileri temel değişiklik '*dosya*'; en iyileştirme analizi değildi en iyileştirme kararları eski olabilir|
|[Önemli hata C1307](../../error-messages/compiler-errors-1/fatal-error-c1307.md)|Profil verileri toplandıktan sonra program düzenlenmiş|
|[Önemli hata C1308](../../error-messages/compiler-errors-1/fatal-error-c1308.md)|*Dosya*: derlemelerin bağlanması desteklenmiyor|
|[Önemli hata C1309](../../error-messages/compiler-errors-1/fatal-error-c1309.md)|C2 eşleşmeyen sürümleri. DLL ve pgodb*ver*. DLL|
|[Önemli hata C1310](fatal-error-c1310.md)|Profil temelli en iyileştirmeler OpenMP ile kullanılamaz|
|[Önemli hata C1311](../../error-messages/compiler-errors-1/fatal-error-c1311.md)|COFF biçimi statik olarak başlatamıyor '*sembol*' ile *numarası* miktarında bir adresi|
|[Önemli hata C1312](fatal-error-c1312.md)|İşlevi çok fazla sayıda koşullu dallanma.  Basitleştirin veya kaynak kodu yeniden düzenleyin.|
|[Önemli hata C1313](../../error-messages/compiler-errors-1/fatal-error-c1313.md)|Derleyici sınırı: *türü* blokları iç içe Geçirilemeyen daha derin *numarası* düzeyleri|
|[Önemli hata C1350](../../error-messages/compiler-errors-1/fatal-error-c1350.md)|DLL yüklenirken hata oluştu '*dosya*': dll bulunamadı|
|[Önemli hata C1351](../../error-messages/compiler-errors-1/fatal-error-c1351.md)|DLL yüklenirken hata oluştu '*dosya*': uyumsuz sürüm|
|[Önemli hata C1352](fatal-error-c1352.md)|Geçersiz veya bozuk MSIL işlevi '*işlevi*'modülünden'*Modülü*'|
|[Önemli hata C1353](fatal-error-c1353.md)|meta veri işlemi başarısız oldu: çalışma zamanı yüklü değil veya sürümü uyuşmuyor|
|[Önemli hata C1382](../../error-messages/compiler-errors-1/fatal-error-c1382.md)|PCH dosyası '*dosya*'beri derlendiğine'*obj*' oluşturuldu. Lütfen bu nesneyi yeniden oluşturun|
|[Önemli hata C1383](fatal-error-c1383.md)|derleyici seçeneği /GL, ortak dil çalışma zamanının yüklü sürümüyle uyumlu değil|
|Önemli hata C1384|Bağlanırken PGO_PATH_TRANSLATION yanlış ayarı '*dosya*'|
|Önemli hata C1451|Concurrency::parallel_for_each için çağrı grafı derlenirken hata ayıklama bilgileri oluşturulamadı: '*çağıran site*'|
|Önemli hata C1505|ayrıştırıcıda bakma hatası|
|[Önemli hata C1506](../../error-messages/compiler-errors-1/fatal-error-c1506.md)|Kurtarılamayan blok kapsamı hatası|
|[Önemli hata C1508](fatal-error-c1508.md)|Derleyici sınırı: '*işlevi*': 65535'ten fazla bağımsız değişken baytı|
|[Önemli hata C1509](../../error-messages/compiler-errors-1/fatal-error-c1509.md)|Derleyici sınırı: çok fazla özel durum işleyici durumlarını işlevindeki '*işlevi*'; işlevi basitleştirin|
|[Önemli hata C1510](../../error-messages/compiler-errors-1/fatal-error-c1510.md)|Cannot open language resource clui.dll|
|[Önemli hata C1601](../../error-messages/compiler-errors-1/fatal-error-c1601.md)|Desteklenmeyen satır içi derleme işlem kodu|
|[Önemli hata C1602](../../error-messages/compiler-errors-1/fatal-error-c1602.md)|desteklenmeyen iç öğe|
|[Önemli hata C1603](../../error-messages/compiler-errors-1/fatal-error-c1603.md)|Satır içi derleme dallanma hedefi je mimo rozsah tarafından *numarası* bayt|
|[Önemli hata C1852](fatal-error-c1852.md)|'*dosya*' geçerli bir ön derlenmiş üstbilgi dosyası değil|
|[Önemli hata C1853](../../error-messages/compiler-errors-1/fatal-error-c1853.md)|'*dosya*' Ön derlenmiş üstbilgi dosyası derleyicinin önceki bir sürümünden olduğu veya önceden derlenmiş üstbilgi C++ ve c (veya tersi) kullanıyorsanız|
|[Önemli hata C1854](../../error-messages/compiler-errors-1/fatal-error-c1854.md)|Nesne dosyasındaki Ön derlenmiş üstbilginin oluşturulması sırasında bilgilerin üzerine yazılamaz: '*dosya*'|
|[Önemli hata C1900](../../error-messages/compiler-errors-1/fatal-error-c1900.md)|Arasında IL uyuşmazlığı '*aracı*'version'*numarası*'ve'*aracı*'version'*sayı*'|
|Önemli hata C1901|İç bellek yönetimi hatası|
|[Önemli hata C1902](../../error-messages/compiler-errors-1/fatal-error-c1902.md)|Program veritabanı yöneticisi uyuşmazlığı; Lütfen yüklemenizi denetleyin|
|[Önemli hata C1903](fatal-error-c1903.md)|Önceki hatalardan kurtarmak alınamıyor; derleme durduruluyor|
|[Önemli hata C1904](fatal-error-c1904.md)|Hatalı sağlayıcı etkileşimi: '*dosya*'|
|[Önemli hata C1905](../../error-messages/compiler-errors-1/fatal-error-c1905.md)|Ön uç ve arka uç uyumlu değil (aynı işlemci hedeflenmelidir).|

## <a name="see-also"></a>Ayrıca bkz.

[C /C++ derleyicisi ve derleme araçları hataları ve Uyarıları](../compiler-errors-1/c-cpp-build-errors.md)
