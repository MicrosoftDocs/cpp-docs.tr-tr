---
title: "NMAKE seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: NMAKE program, options
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef3b987de737d8300f88690754456b73c946180
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-options"></a>NMAKE Seçenekleri
NMAKE seçenekleri aşağıdaki tabloda açıklanmıştır. Seçenekler, eğik çizgi (/) veya tire (-) tarafından öncesinde ve büyük küçük harfe duyarlı değildir. Kullanım [! CMDSWITCHES](../build/makefile-preprocessing-directives.md) derleme görevleri dosyası veya Tools.ini seçenek ayarlarını değiştirmek için.  
  
|Seçenek|Amaç|  
|------------|-------------|  
|/A|Tüm değerlendirilen hedefleri, bağımlılıklar göre değil güncel olması durumunda bile yapısını zorlar. İlişkisiz hedefler derleme zorlamaz.|  
|/B|Zaman damgaları eşit olsa bile zorlar oluşturun. Yalnızca çok hızlı sistemleri (çözünürlük iki saniye veya daha az) için önerilir.|  
|/C|Çıkış, varsayılan önemli olmayan NMAKE hataları veya uyarıları, zaman damgaları ve NMAKE telif hakkı iletisi de dahil olmak üzere gizler. /K. tarafından verilen uyarıları gizler|  
|/D|Bir hedef yoksa her birinin görüntüler zaman damgaları hedef ve bağımlı ve bir ileti değerlendirilir. Derleme görevleri dosyası hata ayıklama için /P ile kullanışlıdır. Kullanım **! CMDSWITCHES** ayarlayın veya derleme görevleri dosyası kısmı için /D temizleyin.|  
|/E|Derleme görevleri dosyası makrosu tanımları geçersiz kılmak ortam değişkenleri neden olur.|  
|/ ERRORREPORT [HİÇBİRİ &#124; İSTEM &#124; SIRA &#124; GÖNDERME]|Çalışma zamanında NMAKE.exe başarısız olursa, iç bu hatalar hakkında bilgi göndermek için/errorreport kullanabilirsiniz.<br /><br /> / Errorreport hakkında daha fazla bilgi için bkz: [/errorreport (dahili derleme hatalarını raporla)](../build/reference/errorreport-report-internal-compiler-errors.md).|  
|/F`filename`|Belirtir `filename` derleme görevleri dosyası olarak. Boşluk veya sekmeleri önünde `filename`. /F kez için her derleme görevleri dosyası belirtin. Standart giriş gelen derleme görevleri dosyası temin etmek için bir tire (-) belirtme `filename`ve klavye girişi F6 veya CTRL + Z ile bitmelidir.|  
|/G|İle birlikte gelen derleme görevleri dosyaları görüntüler! INCLUDE yönergesi.  Bkz: [derleme görevleri dosyası önişleme yönergeleri](../build/makefile-preprocessing-directives.md) daha fazla bilgi için.|  
|/ HELP, /?|NMAKE komut satırı sözdizimi kısa bir özetini görüntüler.|  
|/I|Tüm komutları çıkış kodlarından yok sayar. Ayarlayın veya derleme görevleri dosyası kısmı için /I temizlemek için kullanın **! CMDSWITCHES**. Derleme görevleri dosyası parçası için çıkış kodlarını yoksaymak için bir tire (-) komutu değiştiricisi kullanmayın veya [. Yoksay](../build/dot-directives.md). Her ikisi de belirtilirse/k geçersiz kılar.|  
|/ K|Bir komutu hata verirse ilgisiz bağımlılıkları oluşturmaya devam eder. Ayrıca, bir uyarı verir ve 1 çıkış kodu döndürür. Varsayılan olarak, herhangi bir komutu sıfır olmayan çıkış kodu döndürürse NMAKE durur. / K'den uyarılar /C tarafından bastırılan; Her ikisi de belirtilirse /I/k geçersiz kılar.|  
|/N|Komutlar yürütülürken değil ancak görüntüler; önişlem komutlar yürütülür. Komutları özyinelemeli NMAKE çağrılarında görüntülemez. Derleme görevleri dosyaları hata ayıklama ve zaman damgaları denetimi için kullanışlıdır. Ayarlayın veya derleme görevleri dosyası kısmı için /N temizlemek için kullanın **! CMDSWITCHES**.|  
|/NOLOGO|NMAKE telif hakkı iletisi gizler.|  
|/P|Daha fazla bilgi görüntüler (makrosu tanımları, çıkarım kuralları, hedefler [. SONEKLERİ](../build/dot-directives.md) listesi) için standart çıktı ve yapı çalıştırır. Derleme görevleri dosyası veya komut satırı hedef yok, yalnızca bilgileri görüntüler. Derleme görevleri dosyası hata ayıklamak için /D ile kullanın.|  
|/Q|Hedefleri damgalarının denetler; Yapı çalışmaz. Hiçbir hedef değilse, tüm hedefleri güncel olması durumunda bir sıfır çıkış kodu ve sıfır olmayan çıkış kodu döndürür. Önişlem komutlar yürütülür. Bir toplu iş dosyasından NMAKE çalıştırma kullanışlıdır.|  
|/R|Temizler **. SONEKLERİ** listelemek ve çıkarım kuralları ve Tools.ini dosyasında tanımlanan veya, önceden tanımlanmış makrolar yok sayar.|  
|/ S|Yürütülen komutların görüntülenmesini engeller. Derleme görevleri dosyası kısmen görüntüsünü gizlemek için kullanın  **@**  komutu değiştiricisi veya [. Sessiz](../build/dot-directives.md). Ayarlayın veya derleme görevleri dosyası kısmı için /S temizlemek için kullanın **! CMDSWITCHES**.|  
|/T|Zaman damgaları komut satırı hedefleri (veya ilk derleme görevleri dosyası hedef) güncelleştirir ve önişlem komutları yürütür ancak derleme çalışmaz.|  
|/U|/N. ile birlikte kullanılmalıdır Böylece /N çıktısı bir toplu iş dosyası olarak kullanılabilir, satır içi NMAKE dosyalar dökümünü yapar.|  
|/X`filename`|NMAKE hata çıktısı gönderir `filename` yerine standart hata. Boşluk veya sekmeleri önünde `filename`. Standart çıktıya hata çıkış göndermek için bir tire (-) belirtme `filename`. Standart hata komutları çıktısını etkilemez.|  
|/Y|Toplu iş modu çıkarım kuralları devre dışı bırakır. Bu seçenek belirlendiğinde, tüm toplu iş modu çıkarım kuralları normal çıkarım kuralları kabul edilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Çalıştırma](../build/running-nmake.md)