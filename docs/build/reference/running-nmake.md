---
title: NMAKE Çalıştırma
ms.date: 08/11/2019
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
ms.openlocfilehash: bc274190b64d5340aaac5de594931d4a5333a8c0
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980503"
---
# <a name="running-nmake"></a>NMAKE Çalıştırma

## <a name="syntax"></a>Sözdizimi

> **NMAKE** [*seçenek* ...] [*makrolar* ...] [*hedefler* ...] [ **\@** _komut dosyası_ ...]

## <a name="remarks"></a>Açıklamalar

NMAKE yalnızca belirtilen *hedefleri* veya hiçbiri belirtilmediğinde, derleme görevleri dosyasındaki ilk hedefi oluşturur. İlk makefile hedefi, diğer hedefleri oluşturan bir [sözde hedef](pseudotargets.md) olabilir. NMAKE **/f**ile belirtilen derleme görevleri dosyalarını kullanır veya **/f** belirtilmemişse, geçerli dizindeki makefile dosyası. Derleme görevleri dosyası belirtilmemişse, komut satırı *hedefleri*oluşturmak için çıkarım kurallarını kullanır.

*Komut dosyası* metin dosyası (veya yanıt dosyası) komut satırı girişi içerir. Diğer giriş, *komut dosyasının*önüne \@veya sonra gelmelidir. Bir yola izin verilir. *Komut dosyasında*, satır sonları boşluk olarak değerlendirilir. Makro tanımlarını boşluk içeriyorsa tırnak işaretleri içine alın.

## <a name="nmake-options"></a>NMAKE Seçenekleri

NMAKE seçenekleri aşağıdaki tabloda açıklanmıştır. Seçenekler önünde eğik çizgi (`/`) veya tire (`-`) ve büyük/küçük harfe duyarlı değildir. Derleme [`!CMDSWITCHES`](makefile-preprocessing-directives.md) görevleri dosyası veya Tools. ini içindeki seçenek ayarlarını değiştirmek için kullanın.

| Seçenek | Amaç |
| ------------ | ------------- |
| **SİTEDEKİ** | , Bağımlılara kıyasla güncel olmasalar bile, değerlendirilen tüm hedeflerin derlemesini zorlar. İlişkisiz hedeflerin yapılarını zorlamaz. |
| **/B** | Zaman damgaları eşitse bile derlemeyi zorlar. Yalnızca çok hızlı sistemler için önerilir (iki saniyelik veya daha az çözünürlük). |
| **/C** | Önemli olmayan NMAKE hataları veya uyarıları, zaman damgaları ve NMAKE telif hakkı iletisi dahil olmak üzere varsayılan çıktıyı bastırır. **/K**tarafından verilen uyarıları göstermez. |
| **BELİRTİLMEDİYSE** | Her değerlendirilen hedefin ve bağımlı olduğu zaman damgasını ve bir hedef yoksa bir iletiyi görüntüler. Derleme görevleri dosyası hataları ayıklamak için **/p** ile kullanışlıdır. Makefile `!CMDSWITCHES` 'ın bir parçası için **/d** ayarlamak veya temizlemek için kullanın. |
| **/E** | Ortam değişkenlerinin makefile Makro tanımlarını geçersiz kılmasına neden olur. |
| **/ERRORREPORT** [ **NONE** &#124; **PROMPT** &#124; KUYRUĞU &#124; **GÖNDERME** ] | Çalışma zamanında nmake. exe başarısız olursa, bu iç hatalar hakkında Microsoft 'a bilgi göndermek için **/errorreport** ' u kullanabilirsiniz.<br /><br /> Daha fazla bilgi için bkz. [/errorreport (Iç derleyici hatalarını raporla)](errorreport-report-internal-compiler-errors.md). |
| **/F** *dosya adı* | *Dosya adını* derleme görevleri dosyası olarak belirtir. Boşluk veya sekmeler *Dosya adının*önüne alabilir. Her derleme görevleri için **/f** bir kez belirtin. Standart girişten bir Makefile sağlamak için, *filename*için bir tire (`-`) ve **F6** ya da **CTRL + Z**ile son klavye girişini belirtin. |
| **/G** | `!INCLUDE` Yönergeyle birlikte gelen derleme görevleri dosyalarını öğesini görüntüler. Daha fazla bilgi için bkz. [makefile ön Işleme yönergeleri](makefile-preprocessing-directives.md). |
| **/HELP**, **/?** | NMAKE komut satırı sözdiziminin kısa bir özetini görüntüler. |
| **/I** | Tüm komutlardan çıkış kodlarını yoksayar. Bir Makefile 'ın parçası olarak **/ı** ayarlamak veya temizlemek için kullanın `!CMDSWITCHES`. Bir Makefile 'ın bir parçası için çıkış kodlarını yoksaymak için, bir Dash (`-`) komut değiştiricisi veya [`.IGNORE`](dot-directives.md)kullanın. Her ikisi de belirtilmişse **/k** geçersiz kılar. |
| **K** | Bir komut hata döndürürse ilişkisiz bağımlılıklar oluşturmaya devam eder. Ayrıca bir uyarı yayınlar ve 1 çıkış kodu döndürür. Varsayılan olarak, Eğer herhangi bir komut sıfır dışında çıkış kodu döndürürse nmake durursa. **/K** uyarıları **/c**tarafından bastırılır; **/I** her ikisi de belirtilmişse **/k** öğesini geçersiz kılar. |
| **/N** | Komutları görüntüler ancak yürütmez; ön işleme komutları yürütülür. Özyinelemeli NMAKE çağrılarında komutları görüntülemez. Derleme görevleri dosyalarını hata ayıklamada ve zaman damgalarının denetlenmesi için faydalıdır. Makefile 'ın bir parçası için **/n** ayarlamak veya temizlemek için kullanın `!CMDSWITCHES`. |
| **/NOLOGO** | NMAKE telif hakkı iletisini bastırır. |
| **/P** | Standart çıktıya bilgileri (makro tanımları, çıkarım kuralları, [`.SUFFIXES`](dot-directives.md) hedefler, liste) görüntüler ve sonra derlemeyi çalıştırır. Derleme görevleri dosyası veya komut satırı hedefi yoksa yalnızca bilgileri görüntüler. Derleme görevleri dosyasında hata ayıklamak için **/d** ile kullanın. |
| **ANAHTARIN** | Hedeflerin zaman damgalarını denetler; derlemeyi çalıştırmaz. Tüm hedeflerin güncel olması ve herhangi bir hedefin güncel olup olmadığı sıfır dışı çıkış kodu varsa sıfır çıkış kodu döndürür. Ön işleme komutları yürütülür. Bir toplu iş dosyasından NMAKE çalıştırılırken yararlı olur. |
| **/R** | `.SUFFIXES` Listeyi temizler ve Tools. ini dosyasında tanımlanan veya önceden tanımlanmış olan çıkarım kurallarını ve makroları yoksayar. |
| **SN** | Yürütülen komutların görüntülenmesini önler. Makefile 'ın bir parçası olarak görüntülenmesini engellemek için, veya **\@** [`.SILENT`](dot-directives.md)komut değiştiricisini kullanın. Bir Makefile 'ın bir parçası için **/s** ayarlamak veya temizlemek için kullanın `!CMDSWITCHES`. |
| **/T** | Komut satırı hedeflerinin (veya ilk derleme görevleri dosyası hedefi) zaman damgalarını güncelleştirir ve ön işleme komutlarını yürütür ancak derlemeyi çalıştırmaz. |
| **P** | **/N**ile birlikte kullanılmalıdır. Satır içi NMAKE dosyalarını, **/n** çıktısının bir toplu iş dosyası olarak kullanılabilmesi için döker. |
| **/X** *dosya adı* | NMAKE hata çıkışını standart hata yerine *dosya adına* gönderir. Boşluk veya sekmeler *Dosya adının*önüne alabilir. Standart çıktıya hata çıktısı göndermek için *dosya adı*için bir tire (`-`) belirtin. Komutlardan standart hataya kadar olan çıktıyı etkilemez. |
| **/Y** | Batch modu çıkarımı kurallarını devre dışı bırakır. Bu seçenek belirlendiğinde, tüm toplu işlem modu çıkarımı kuralları düzenli çıkarım kuralları olarak değerlendirilir. |

## <a name="toolsini-and-nmake"></a>Tools.ini ve NMAKE

NMAKE, **/r** kullanılmadığı takdirde makefiles 'ı okumadan önce Tools. ini okur. Önce geçerli dizinde ve ardından INIT ortam değişkeni tarafından belirtilen dizinde Tools. ini dosyasını arar. Başlatma dosyasındaki NMAKE ayarlarının bölümü ile `[NMAKE]` başlar ve derleme görevleri dosyası bilgileri içerebilir. Numara işareti (`#`) ile başlayan ayrı bir satırda bir açıklama belirtin.

## <a name="exit-codes-from-nmake"></a>NMAKE Çıkış Kodları

NMAKE şu çıkış kodlarını döndürür:

| Kod | Anlamı |
| ---------- | ------------- |
| 0 | Hata yok (muhtemelen bir uyarı) |
| 1\. | Tamamlanmamış derleme (yalnızca **/k** kullanıldığında verilir) |
| 2 | Program hatası, muhtemelen şu sorunlardan biri neden oldu:<br /> -Derleme görevleri dosyasında sözdizimi hatası<br /> -Bir komuttan bir hata veya çıkış kodu<br /> -Kullanıcı tarafından bir kesinti |
| 4 | Sistem hatası — bellek yetersiz |
| 255 | Hedef güncel değil (yalnızca **/q** kullanıldığında verilir) |

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
