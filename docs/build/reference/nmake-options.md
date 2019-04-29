---
title: NMAKE Seçenekleri
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, options
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
ms.openlocfilehash: c60b6d821d8e16e87f86e3b79825aa1dee7867c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320545"
---
# <a name="nmake-options"></a>NMAKE Seçenekleri

NMAKE seçenekleri aşağıdaki tabloda açıklanmıştır. Seçenekler, eğik çizgi (/) veya tire (-) tarafından öncesinde ve büyük/küçük harfe duyarlı değildir. Kullanım [! CMDSWITCHES](makefile-preprocessing-directives.md) derleme görevleri dosyası veya Tools.ini seçenek ayarlarını değiştirmek için.

|Seçenek|Amaç|
|------------|-------------|
|/A|Tüm değerlendirilen hedeflere göre bağımlılıklar değil güncel olması durumunda bile yapısını zorlar. İlgisiz hedefler yapısını zorlamaz.|
|/B|Zaman damgaları eşitse bile zorlar oluşturun. Yalnızca çok hızlı sistemleri (çözüm iki saniye veya daha az) için önerilir.|
|/C|NMAKE önemli olmayan hataları veya uyarıları, zaman damgaları ve NMAKE telif hakkı iletisini gibi çıkış, varsayılan bastırır. /K. tarafından verilen uyarıları bastırır|
|/D|Bir hedef mevcut değil, hedef ve bağımlı ve bir ileti görüntüler zaman damgaları her değerlendirilir. Derleme görevleri dosyası hata ayıklama için /P ile yararlıdır. Kullanım **! CMDSWITCHES** veya derleme görevleri dosyası parçası için /D temizleyin.|
|/E|Derleme görevleri dosyası makro tanımları geçersiz kılmak ortam değişkenlerini neden olur.|
|/ ERRORREPORT [NONE &AMP;#124; İSTEMİ &AMP;#124; KUYRUK &AMP;#124; GÖNDER]|Çalışma zamanında NMAKE.exe başarısız olursa, bu iç hataları hakkında Microsoft'a bilgi/errorreport kullanabilirsiniz.<br /><br /> / Errorreport hakkında daha fazla bilgi için bkz: [/errorreport (dahili derleme hatalarını raporla)](errorreport-report-internal-compiler-errors.md).|
|/F *dosya adı*|Belirtir *filename* derleme görevleri dosyası olarak. Boşluk veya sekme önünde *filename*. /F kez için her bir derleme görevleri dosyası belirtin. Standart girişten alınan bir derleme görevleri dosyası temin etmek için bir tire (-) belirtme *filename*ve klavye girdisi F6 ya da CTRL + Z ile bitmelidir.|
|/G|Bulunan derleme görevleri dosyalarını görüntüler! INCLUDE yönergesi.  Bkz: [derleme görevleri dosyası önişleme yönergeleri](makefile-preprocessing-directives.md) daha fazla bilgi için.|
|/ HELP, /?|NMAKE komut satırı sözdizimi kısa bir özetini görüntüler.|
|/I|Tüm komutlarından çıkış kodlarını dikkate almaz. Ayarlayın veya derleme görevleri dosyası parçası için /I temizlemek için kullanın **! CMDSWITCHES**. Derleme görevleri dosyası bölümü için çıkış kodları yoksaymak için bir tire (-) komut değiştiricisini kullanın veya [. Yoksay](dot-directives.md). Her ikisi de belirtilirse /K geçersiz kılar.|
|/K|Bir komut hata verirse ilgisiz bağımlılıkları oluşturmaya devam eder. Ayrıca bir uyarı verir ve bir çıkış kodu 1 döndürür. Varsayılan olarak, herhangi bir komutu bir sıfır olmayan çıkış kodu döndürürse NMAKE durdurur. /K gelen uyarılar /C tarafından bastırılan; Her ikisi de belirtilirse /I /K geçersiz kılar.|
|/N|Görüntüler ancak komutları yürütmez. Ön işlem komutları yürütülür. Komutları özyinelemeli NMAKE çağrılarında görüntülemez. Derleme görevleri dosyası hata ayıklama ve zaman damgaları denetimi için kullanışlıdır. Ayarlayın veya derleme görevleri dosyası parçası için /N temizlemek için kullanın **! CMDSWITCHES**.|
|/NOLOGO|NMAKE telif hakkı iletisini görüntüler.|
|/P|Daha fazla bilgi görüntüler (makro tanımları, çıkarım kuralları, hedefler [. SONEKLERİ](dot-directives.md) listesi) için standart çıktı ve ardından yapı çalıştırır. Herhangi bir derleme görevleri dosyası veya komut satırı hedef varsa, yalnızca bilgileri görüntüler. /D ile bir derleme görevleri dosyası hata ayıklama için kullanın.|
|/Q|Denetimleri zaman damgaları hedefleri; derleme çalıştırmaz. Herhangi bir hedef değil tüm hedefleri güncel olması durumunda bir sıfır çıkış kodu ve sıfır olmayan çıkış kodu döndürür. Ön işlem komutları yürütülür. Bir toplu iş dosyasından NMAKE çalıştırma kullanışlıdır.|
|/R|Temizler **. SONEKLERİ** listelemek ve çıkarım kuralları ve Tools.ini dosyasında tanımlı veya, önceden tanımlanmış makrolar yok sayar.|
|/S|Yürütülen komutlar görüntülenmesini bastırır. Kısmi derleme görevleri dosyası görüntülenmesini engellemek için kullanın **\@** komut değiştiricisi veya [. Sessiz](dot-directives.md). Ayarlayın veya derleme görevleri dosyası parçası için /S temizlemek için kullanın **! CMDSWITCHES**.|
|/T|Zaman damgaları komut satırı hedefleri (veya ilk derleme görevleri dosyası hedef) güncelleştirir ve ön işlem komutları yürütür, ancak yapı çalışmaz.|
|/U|/N. ile birlikte kullanılmalıdır /N çıkış bir toplu iş dosyası olarak kullanılabilir, böylece satır içi NMAKE dosyaları dökümünü yapar.|
|/X *dosya adı*|NMAKE hata çıktısı gönderir *filename* yerine standart hata. Boşluk veya sekme önünde *filename*. Hata çıktısını standart çıktıya göndermek için bir tire (-) belirtme *filename*. Standart hata komutları çıktısını etkilemez.|
|/Y|Toplu iş modu çıkarım kuralları devre dışı bırakır. Tüm toplu iş modu çıkarım kuralları, bu seçenek belirlendiğinde, normal çıkarım kuralları kabul edilir.|

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Çalıştırma](running-nmake.md)
