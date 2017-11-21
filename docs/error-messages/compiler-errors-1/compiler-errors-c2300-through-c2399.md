---
title: "C2300 ile c2399 arasındaki derleyici hataları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
helpviewer_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
dev_langs: C++
ms.assetid: 07ca45b5-b2f0-4049-837b-40a7a3caed88
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f8e1dcf350c974f5be96b971d3d70e69b95ebc9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-errors-c2300-through-c2399"></a>C2300 ile C2399 Arasındaki Derleyici Hataları
Bu bölümü belgelerin makalelerinde Visual C++ derleyici hataları alt hakkında bilgiler içerir. Burada yer alan bilgiler erişebilir veya **çıkış** penceresi Visual Studio'da bir hata numarası seçin ve ardından F1 tuşuna belirtin.  
  
> [!NOTE]
>  Her [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] hata MSDN içinde belgelenmiştir. Çoğu durumda, tanılama iletisinin tüm kullanılabilir bilgileri sağlar. Bir hata iletisi düşünüyorsanız, ek açıklama, bize bildirin gerekir. Bilgisayarınıza bu sayfadaki geri bildirim formu kullanın veya Visual Studio menü çubuğunda gidin ve seçebilirsiniz **yardımcı**, **bir hata raporu**, veya üzerinde bir öneri veya hata raporu gönderebilirsiniz [Microsoft Connect](http://connect.microsoft.com/VisualStudio).  
  
 Hatalar ve uyarılar MSDN ortak forumlarda için Ek Yardım bulabilirsiniz. [Visual C++ dili](http://go.microsoft.com/fwlink/?LinkId=158195) forumudur sorular ve tartışmaları hakkında [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] dili sözdizimi ve derleyicisi. [Visual C++ genel](http://go.microsoft.com/fwlink/?LinkId=158194) Forumu hakkında sorular için olan [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] , değil tartışılır diğer forumlarda. Üzerinde hataları ve Uyarıları hakkında Yardım bulabilirsiniz [yığın taşması](http://stackoverflow.com/).  
  
|Hata|İleti|  
|-----------|-------------|  
|[Derleyici Hatası C2300](compiler-error-c2300.md)|'*sınıfı*': sınıf adı verilen bir yıkıcı yok ' ~*sınıfı*'|  
|[Derleyici Hatası C2301](compiler-error-c2301.md)|Sol ' -> ~*tanımlayıcısı*' yapısı/sınıfı/UNION işaret etmesi gerekir|  
|[Derleyici Hatası C2302](compiler-error-c2302.md)|Sol '. ~*tanımlayıcısı*' struct/sınıfı/union türünde olmalıdır|  
|Derleyici Hatası C2303|Yapılandırılmış özel durum işleme bir coroutine kullanılamaz|  
|Derleyici Hatası C2304|'*anahtar sözcüğü*' catch bloğu içinde kullanılamaz|  
|Derleyici Hatası C2305|'*dosya*' Bu modül için hata ayıklama bilgilerini içermiyor.|  
|Derleyici Hatası C2306|'*dosya*' Bu modül için en son hata ayıklama bilgilerini içermiyor.|  
|[Derleyici Hatası C2307](compiler-error-c2307.md)|pragma *yönergesi* Artımlı derleme etkinleştirilirse dışında işlevi taşınmalıdır|  
|[Derleyici Hatası C2308](compiler-error-c2308.md)|eşleşmeyen dizeleri birleştirme|  
|[Derleyici Hatası C2309](compiler-error-c2309.md)|catch işleyicisi parantez içine alınmış özel durum bildirimi bekleniyor|  
|[Derleyici Hatası C2310](compiler-error-c2310.md)|catch işleyicileri bir türü belirtmelisiniz|  
|[Derleyici Hatası C2311](compiler-error-c2311.md)|'*türü*': satırındaki '...' tarafından yakalanan *numarası*|  
|[Derleyici Hatası C2312](compiler-error-c2312.md)|'*type1*': tarafından yakalanan '*type2*' satırındaki *numarası*|  
|[Derleyici Hatası C2313](compiler-error-c2313.md)|'*type1*': başvuru tarafından yakalanan ('*type2*') satırındaki *numarası*|  
|Derleyici Hatası C2314|anahtar sözcüğü '*keyword1*' kullanım dışıdır: kullanmak '*keyword2*' yerine|  
|[Derleyici Hatası C2315](compiler-error-c2315.md)|'*type1*': başvuru yakalandı tarafından '*type2*' satırındaki *numarası*|  
|[Derleyici Hatası C2316](compiler-error-c2316.md)|'*türü*': yıkıcı ve/veya kopya Oluşturucu erişilemez veya silinmiş olduğundan yakalanan olamaz|  
|[Derleyici Hatası C2317](compiler-error-c2317.md)|'satırında başlatma bloğu deneyin' '*numarası*' catch işleyicileri sahip|  
|[Derleyici Hatası C2318](compiler-error-c2318.md)|Bu yakalama işleyici ile ilişkili herhangi bir try engelleme|  
|[Derleyici Hatası C2319](compiler-error-c2319.md)|Bileşik deyim tarafından ' try/catch' gelmelidir. Eksik ' {'|  
|[Derleyici Hatası C2320](compiler-error-c2320.md)|Beklenen ':' erişim belirticisi izlemek için '*belirticisi*'|  
|Derleyici Hatası C2321|'*tanımlayıcısı*' bir anahtar sözcüktür ve bu bağlamda kullanılamaz|  
|[Derleyici Hatası C2322](compiler-error-c2322.md)|'*tanımlayıcısı*': dllimport adresini '*tanımlayıcısı*' statik değil|  
|Derleyici Hatası C2323|'*tanımlayıcısı*': üye olmayan işleci yeni ya da silme işlevleri bildirilmemiş statik veya farklı bir ad alanında genel ad alanı dışında|  
|[Derleyici Hatası C2324](compiler-error-c2324.md)|'*tanımlayıcısı*': sağındaki beklenmeyen ':: ~'|  
|[Derleyici Hatası C2325](compiler-error-c2325.md)|'*type1*': beklenmeyen türü sağ tarafındaki ' -> ~': beklenen '*type2*'|  
|[Derleyici Hatası C2326](compiler-error-c2326.md)|'*bildirimcisi*': işlevi erişemiyor '*tanımlayıcısı*'|  
|[Derleyici Hatası C2327](compiler-error-c2327.md)|'*tanımlayıcısı*': tür adı, statik ya da Numaralandırıcı değil|  
|Derleyici Hatası C2328|'*anahtar sözcüğü*': anahtar sözcüğü henüz desteklenmiyor|  
|Derleyici Hatası C2329|'*tanımlayıcısı*': __ptr64 işlev işaretçileri için kullanılamaz|  
|Derleyici Hatası C2330|'implementation_key ()' #pragma start_map_region/stop_map_region tarafından sınırlanmış bir bölgede yalnızca geçerlidir|  
|Derleyici Hatası C2331|Erişim '*tanımlayıcısı*'olarak şimdi tanımlanan'*accessibility1*', daha önce olarak tanımlandı'*accessibility2*'|  
|[Derleyici Hatası C2332](compiler-error-c2332.md)|'*typedef*': Etiket adı eksik|  
|[Derleyici Hatası C2333](compiler-error-c2333.md)|'*işlevi*': işlevi bildiriminde hata; işlev gövdesi atlanıyor|  
|[Derleyici Hatası C2334](compiler-error-c2334.md)|Önceki beklenmeyen belirteçleri '*belirteci*'; görünen işlev gövdesi atlanıyor|  
|Derleyici Hatası C2335|'*tanımlayıcısı*': türü bir işlev parametresi listesinde tanıtılamaz|  
|Derleyici Hatası C2336|'*türü*': türü geçersiz|  
|[Derleyici Hatası C2337](compiler-error-c2337.md)|'*özniteliği*': öznitelik bulunamadı|  
|[Derleyici Hatası C2338](compiler-error-c2338.md)|*(Dış sağlayıcı hata iletisinden)*|  
|Derleyici Hatası C2339|'*tanımlayıcısı*': Katıştırılmış IDL geçersiz türü|  
|Derleyici Hatası C2340|'*tanımlayıcısı*': 'static' yalnızca kullanılabilir bir sınıf tanımı içinde|  
|[Derleyici Hatası C2341](compiler-error-c2341.md)|'*bölüm*': segment #pragma data_seg, code_seg veya önceki bölümde kullanılacak kullanılarak tanımlanması gerekir|  
|Derleyici Hatası C2342|sözdizimi hatası: çakışan tür niteleyicileri|  
|Derleyici Hatası C2343|'*bölüm*': çakışan bölüm öznitelikleri|  
|[Derleyici Hatası C2344](compiler-error-c2344.md)|Hizalama (*numarası*): hizalama iki güç olması gerekir|  
|[Derleyici Hatası C2345](compiler-error-c2345.md)|Hizalama (*numarası*): Geçersiz hizalama değeri|  
|[Derleyici Hatası C2346](compiler-error-c2346.md)|'*işlevi*' yerel olarak derlenemez: '*açıklama*'|  
|Derleyici Hatası C2347|Kullanımdan kalktı.|  
|[Derleyici Hatası C2348](compiler-error-c2348.md)|'*türü*': C-style Toplama ifadesi değil, katıştırılmış-IDL dışarı aktarılamaz|  
|[Derleyici Hatası C2349](compiler-error-c2349.md)|'*işlevi*' yönetilen olarak derlenemez: '*açıklama*'; yönetilmeyen #pragma kullanın|  
|[Derleyici Hatası C2350](compiler-error-c2350.md)|'*tanımlayıcısı*' statik üyesi değil|  
|[Derleyici Hatası C2351](compiler-error-c2351.md)|artık kullanılmayan C++ oluşturucusu başlatma sözdizimi|  
|[Derleyici Hatası C2352](compiler-error-c2352.md)|'*tanımlayıcısı*': geçersiz bir statik olmayan üye işlevi çağrısı|  
|[Derleyici Hatası C2353](compiler-error-c2353.md)|özel durum belirtimine izin verilmez|  
|Derleyici Hatası C2354|Kullanımdan kalktı.|  
|[Derleyici Hatası C2355](compiler-error-c2355.md)|'this': yalnızca statik olmayan üye işlevleri veya statik olmayan veri üyesi başlatıcıları içinde başvurulabilir|  
|[Derleyici Hatası C2356](compiler-error-c2356.md)|başlatma segment çeviri birim sırasında değiştirmemeniz gerekir|  
|[Derleyici Hatası C2357](compiler-error-c2357.md)|'*tanımlayıcısı*': türünde bir işlev olmalıdır '*türü*'|  
|Derleyici Hatası C2358|'*tanımlayıcısı*': bir sınıf tanımı dışında bir statik özellik tanımlanamıyor|  
|Derleyici Hatası C2359|Kullanımdan kalktı.|  
|[Derleyici Hatası C2360](compiler-error-c2360.md)|Başlatma '*tanımlayıcısı*' 'case' etiketle atlandı|  
|[Derleyici Hatası C2361](compiler-error-c2361.md)|Başlatma '*tanımlayıcısı*' 'default' etiketle atlandı|  
|[Derleyici Hatası C2362](compiler-error-c2362.md)|Başlatma '*tanımlayıcısı*' tarafından Atlanan ' goto *etiket*'|  
|Derleyici Hatası C2363|derleyici iç sayısal sınırı işlevi bir dize değişmez değer bağımsız değişken gerektirir|  
|[Derleyici Hatası C2364](compiler-error-c2364.md)|'*türü*': özel özniteliği için geçersiz tür|  
|[Derleyici Hatası C2365](compiler-error-c2365.md)|'*Üye1*': şemadaki; önceki tanımı edildi '*üye2*'|  
|Derleyici Hatası C2366|'*tanımlayıcısı*': şemadaki; farklı implementation_key tanımlayıcıları|  
|Derleyici Hatası C2367|Kullanımdan kalktı.|  
|[Derleyici Hatası C2368](compiler-error-c2368.md)|'*tanımlayıcısı*': şemadaki; farklı ayırma tanımlayıcıları|  
|[Derleyici Hatası C2369](compiler-error-c2369.md)|'*tanımlayıcısı*': şemadaki; farklı alt simgeler|  
|[Derleyici Hatası C2370](compiler-error-c2370.md)|'*tanımlayıcısı*': şemadaki; farklı depolama sınıfı|  
|[Derleyici Hatası C2371](compiler-error-c2371.md)|'*tanımlayıcısı*': şemadaki; farklı temel türleri|  
|[Derleyici Hatası C2372](compiler-error-c2372.md)|'*tanımlayıcısı*': şemadaki; yöneltme farklı türleri|  
|[Derleyici Hatası C2373](compiler-error-c2373.md)|'*tanımlayıcısı*': şemadaki; farklı tür değiştiricileri|  
|[Derleyici Hatası C2374](compiler-error-c2374.md)|'*tanımlayıcısı*': şemadaki; birden çok başlatma|  
|[Derleyici Hatası C2375](compiler-error-c2375.md)|'*tanımlayıcısı*': şemadaki; farklı bağlantı|  
|[Derleyici Hatası C2376](compiler-error-c2376.md)|'*tanımlayıcısı*': şemadaki; farklı göre ayırma|  
|[Derleyici Hatası C2377](compiler-error-c2377.md)|'*tanımlayıcısı*': şemadaki; typedef başka bir simge ile aşırı olamaz|  
|[Derleyici Hatası C2378](compiler-error-c2378.md)|'*tanımlayıcısı*': şemadaki; simgesi ile typedef aşırı olamaz|  
|[Derleyici Hatası C2379](compiler-error-c2379.md)|biçimsel parametresi *numarası* yükseltilmiş zaman farklı türüne sahip|  
|[Derleyici Hatası C2380](compiler-error-c2380.md)|türde önceki '*tanımlayıcısı*' (oluşturucu dönüş türü veya geçerli sınıf adı geçersiz yeniden tanımlama?)|  
|[Derleyici Hatası C2381](compiler-error-c2381.md)|'*tanımlayıcısı*': şemadaki; '__declspec(noreturn)' veya '[[noreturn]]' farklıdır|  
|[Derleyici Hatası C2382](compiler-error-c2382.md)|'*tanımlayıcısı*': şemadaki; farklı bir özel durum belirtimleri|  
|[Derleyici Hatası C2383](compiler-error-c2383.md)|'*tanımlayıcısı*': varsayılan bağımsız değişkenler üzerinde bu simgeyi izin verilmez|  
|[Derleyici Hatası C2384](compiler-error-c2384.md)|'*üye*': thread_local veya __declspec(thread) yönetilen WinRT sınıf üyesine uygulayamazsınız|  
|[Derleyici Hatası C2385](compiler-error-c2385.md)|Belirsiz erişimini '*üye*'|  
|[Derleyici Hatası C2386](compiler-error-c2386.md)|'*tanımlayıcısı*': Bu ada sahip bir sembolü geçerli kapsamda zaten var.|  
|[Derleyici Hatası C2387](compiler-error-c2387.md)|'*tanımlayıcısı*': belirsiz taban sınıfı|  
|[Derleyici Hatası C2388](compiler-error-c2388.md)|'*tanımlayıcısı*': __declspec(appdomain) ve __declspec(process) ile bir simge bildirilemez|  
|[Derleyici Hatası C2389](compiler-error-c2389.md)|'*işleci*': Geçersiz işleneni 'nullptr'|  
|[Derleyici Hatası C2390](compiler-error-c2390.md)|'*tanımlayıcısı*': hatalı depolama sınıfı*belirticisi*'|  
|[Derleyici Hatası C2391](compiler-error-c2391.md)|'*tanımlayıcısı*': 'friend' tür tanımı sırasında kullanılamaz|  
|[Derleyici Hatası C2392](compiler-error-c2392.md)|'*Üye1*': türler yönetilen WinRT türlerinde, aksi takdirde desteklenmez eşdeğişken döndürür '*üye2*' geçersiz kılınabilir|  
|[Derleyici Hatası C2393](compiler-error-c2393.md)|'*simgesi*': appdomain başına simgesi kesimdeki ayrılamıyor '*segment*'|  
|[Derleyici Hatası C2394](compiler-error-c2394.md)|'*türü*:: işleci *işleci*': CLR/WinRT işleci geçerli değil. En az bir parametre aşağıdaki türden olması gerekir: 'T ^', 'T ^ %', 'T ^ &', burada T = '*türü*'|  
|[Derleyici Hatası C2395](compiler-error-c2395.md)|'*türü*:: işleci *işleci*': CLR/WinRT işleci geçerli değil. En az bir parametre aşağıdaki türden olması gerekir: 'T', 'T %', 'T &', 'T ^', 'T ^ %', 'T ^ &', burada T = '*türü*'|  
|[Derleyici Hatası C2396](compiler-error-c2396.md)|'*type1*:: işleci *type2*': CLR/WinRT dönüştürme kullanıcı tanımlı işlev geçerli değil. Dönüştür veya Dönüştür: 'T ^', 'T ^ %', 'T ^ &', burada T = '*type1*'|  
|[Derleyici Hatası C2397](compiler-error-c2397.md)|Dönüştürme '*type1*'to'*type2*' daraltma dönüştürme gerektirir|  
|Derleyici Hatası c2398 arasındaki|Öğe '*numarası*': dönüştürme '*type1*'to'*type2*' daraltma dönüştürme gerektirir|  
|Derleyici Hatası c2399 arasındaki|Kullanımdan kalktı.|  
