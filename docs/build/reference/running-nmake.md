---
title: NMAKE Çalıştırma
description: Microsoft NMAKE komut satırı seçeneklerine yönelik başvuru kılavuzu.
ms.date: 02/09/2020
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
ms.openlocfilehash: bfada33a89c04d25bf7444cbf3b1e7ef3ed44385
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417294"
---
# <a name="running-nmake"></a>NMAKE Çalıştırma

## <a name="syntax"></a>Sözdizimi

> **NMAKE** [*seçenek* ...] [*makrolar* ...] [*hedefler* ...] [ **\@** _komut-dosya_ ...]

## <a name="remarks"></a>Açıklamalar

NMAKE yalnızca belirtilen *hedefleri* veya hiçbiri belirtilmediğinde, derleme görevleri dosyasındaki ilk hedefi oluşturur. İlk makefile hedefi, diğer hedefleri oluşturan bir [sözde hedef](description-blocks.md#pseudotargets) olabilir. NMAKE **/f**ile belirtilen derleme görevleri dosyalarını kullanır veya **/f** belirtilmemişse, geçerli dizindeki makefile dosyası. Derleme görevleri dosyası belirtilmemişse, komut satırı *hedefleri*oluşturmak için çıkarım kurallarını kullanır.

*Komut dosyası* metin dosyası (veya yanıt dosyası) komut satırı girişi içerir. Diğer giriş \@*komut dosyasının*önüne veya sonra gelmelidir. Bir yola izin verilir. *Komut dosyasında*, satır sonları boşluk olarak değerlendirilir. Makro tanımlarını boşluk içeriyorsa tırnak işaretleri içine alın.

## <a name="nmake-options"></a>NMAKE Seçenekleri

NMAKE seçenekleri aşağıdaki tabloda açıklanmıştır. Seçenekler önünde eğik çizgi (`/`) veya tire (`-`) ve büyük/küçük harfe duyarlı değildir. Derleme görevleri dosyası veya Tools. ini içindeki seçenek ayarlarını değiştirmek için [`!CMDSWITCHES`](makefile-preprocessing-directives.md) kullanın.

| Seçenek | Amaç |
| ------------ | ------------- |
| **Sitedeki** | , Bağımlılara kıyasla güncel olmasalar bile, değerlendirilen tüm hedeflerin derlemesini zorlar. İlişkisiz hedeflerin yapılarını zorlamaz. |
| **/B** | Zaman damgaları eşitse bile derlemeyi zorlar. Yalnızca hızlı sistemler için önerilir (iki saniyelik veya daha az çözünürlük). |
| **/C** | Önemli olmayan NMAKE hataları veya uyarıları, zaman damgaları ve NMAKE telif hakkı iletisi dahil olmak üzere varsayılan çıktıyı bastırır. **/K**tarafından verilen uyarıları göstermez. |
| **Belirtilmediyse** | Her değerlendirilen hedefin ve bağımlı olduğu zaman damgasını ve bir hedef yoksa bir iletiyi görüntüler. Derleme görevleri dosyası hataları ayıklamak için **/p** ile kullanışlıdır. Makefile 'ın bir parçası olarak **/d** ayarlamak veya temizlemek için `!CMDSWITCHES` kullanın. |
| **/E** | Ortam değişkenlerinin makefile Makro tanımlarını geçersiz kılmasına neden olur. |
| **/errorreport** [ **yok** &#124; **Prompt** &#124; **kuyruğu** &#124; **gönderme** ] | Kullanım dışı. [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları denetim raporlaması. |
| **/F** *dosya adı* | *Dosya adını* derleme görevleri dosyası olarak belirtir. Boşluk veya sekmeler *Dosya adının*önüne alabilir. Her derleme görevleri için **/f** bir kez belirtin. Standart girişten bir Makefile sağlamak için, *filename*için bir tire (`-`) ve **F6** ya da **CTRL + Z**ile son klavye girişini belirtin. |
| **/G** | `!INCLUDE` yönergesine dahil olan derleme görevleri dosyalarını öğesini görüntüler. Daha fazla bilgi için bkz. [makefile ön Işleme yönergeleri](makefile-preprocessing-directives.md). |
| **/Help**, **/?** | NMAKE komut satırı sözdiziminin kısa bir özetini görüntüler. |
| **/I** | Tüm komutlardan çıkış kodlarını yoksayar. Bir Makefile 'ın parçası olarak **/ı** ayarlamak veya temizlemek için `!CMDSWITCHES`kullanın. Makefile 'ın bir parçası için çıkış kodlarını yoksaymak için, bir tire (`-`) komut değiştiricisi veya [`.IGNORE`](dot-directives.md)kullanın. Her ikisi de belirtilmişse **/k** geçersiz kılar. |
| **K** | Bir komut hata döndürürse ilişkisiz bağımlılıklar oluşturmaya devam eder. Ayrıca bir uyarı yayınlar ve 1 çıkış kodu döndürür. Varsayılan olarak, Eğer herhangi bir komut sıfır dışında çıkış kodu döndürürse nmake durursa. **/K** uyarıları **/c**tarafından bastırılır; **/I** her ikisi de belirtilmişse **/k** öğesini geçersiz kılar. |
| **/N** | Komutları görüntüler ancak yürütmez; ön işleme komutları yürütülür. Özyinelemeli NMAKE çağrılarında komutları görüntülemez. Derleme görevleri dosyalarını hata ayıklamada ve zaman damgalarının denetlenmesi için faydalıdır. Makefile 'ın bir parçası için **/n** ayarlamak veya temizlemek için `!CMDSWITCHES`kullanın. |
| **/NOLOGO** | NMAKE telif hakkı iletisini bastırır. |
| **/P** | Bilgileri (makro tanımları, çıkarım kuralları, hedefler, [`.SUFFIXES`](dot-directives.md) listesi) standart çıktıya görüntüler ve sonra derlemeyi çalıştırır. Derleme görevleri dosyası veya komut satırı hedefi yoksa yalnızca bilgileri görüntüler. Derleme görevleri dosyasında hata ayıklamak için **/d** ile kullanın. |
| **Anahtarın** | Hedeflerin zaman damgalarını denetler; derlemeyi çalıştırmaz. Tüm hedefler güncel ise sıfır çıkış kodu ve herhangi bir hedefin güncel olup olmadığını sıfır dışında bir çıkış kodu döndürür. Ön işleme komutları yürütülür. Bir toplu iş dosyasından NMAKE çalıştırılırken yararlı olur. |
| **/R** | `.SUFFIXES` listesini temizler ve Tools. ini dosyasında tanımlanan veya önceden tanımlanmış olan çıkarım kurallarını ve makroları yoksayar. |
| **Sn** | Yürütülen komutların görüntülenmesini önler. Makefile 'ın bir parçası olarak görüntülenmesini engellemek için **\@** komut değiştiricisini veya [`.SILENT`](dot-directives.md)kullanın. Bir Makefile 'ın bir parçası olarak **/s** ayarlamak veya temizlemek için `!CMDSWITCHES`kullanın. |
| **/T** | Komut satırı hedeflerinin (veya ilk derleme görevleri dosyası hedefi) zaman damgalarını güncelleştirir ve ön işleme komutlarını yürütür ancak derlemeyi çalıştırmaz. |
| **P** | **/N**ile birlikte kullanılmalıdır. Satır içi NMAKE dosyalarını, **/n** çıktısının bir toplu iş dosyası olarak kullanılabilmesi için döker. |
| **/X** *dosya adı* | NMAKE hata çıkışını standart hata yerine *dosya adına* gönderir. Boşluk veya sekmeler *Dosya adının*önüne alabilir. Hata çıkışını standart çıktıya göndermek için *dosya adı*için bir tire (`-`) belirtin. Komutlardan standart hataya kadar olan çıktıyı etkilemez. |
| **/Y** | Batch modu çıkarımı kurallarını devre dışı bırakır. Bu seçenek belirlendiğinde, tüm toplu işlem modu çıkarımı kuralları düzenli çıkarım kuralları olarak değerlendirilir. |

## <a name="toolsini-and-nmake"></a>Tools.ini ve NMAKE

NMAKE, **/r** kullanılmadığı takdirde makefiles 'ı okumadan önce Tools. ini okur. Önce geçerli dizinde ve ardından INIT ortam değişkeni tarafından belirtilen dizinde Tools. ini dosyasını arar. Başlatma dosyasındaki NMAKE ayarlarının bölümü `[NMAKE]` ile başlar ve derleme görevleri dosyası bilgileri içerebilir. Numara işareti (`#`) ile başlayan ayrı bir satırda bir açıklama belirtin.

## <a name="exit-codes-from-nmake"></a>NMAKE Çıkış Kodları

NMAKE şu çıkış kodlarını döndürür:

| Kod | Açıklama |
| ---------- | ------------- |
| 0 | Hata yok (muhtemelen bir uyarı) |
| 1\. | Tamamlanmamış derleme (yalnızca **/k** kullanıldığında verilir) |
| 2 | Program hatası, muhtemelen şu sorunlardan biri neden oldu:<br /> -Derleme görevleri dosyasında sözdizimi hatası<br /> -Bir komuttan bir hata veya çıkış kodu<br /> -Kullanıcı tarafından bir kesinti |
| 4 | Sistem hatası — bellek yetersiz |
| 255 | Hedef güncel değil (yalnızca **/q** kullanıldığında verilir) |

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
