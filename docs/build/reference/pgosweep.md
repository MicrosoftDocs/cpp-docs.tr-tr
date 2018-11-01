---
title: pgosweep
ms.date: 03/14/2018
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
ms.openlocfilehash: 6e03285942b60a5c9b5647c6bb3f12cc40b0a396
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428516"
---
# <a name="pgosweep"></a>pgosweep

Profil temelli iyileştirme, tüm profil verilerini çalışan bir programı .pgc dosyaya yazmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **pgosweep** [*seçenekleri*] *görüntü* *pgcfile*

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
(İsteğe bağlı) İçin geçerli değerleri *seçenekleri* şunlardır:

- **/?** veya **/help** yardım iletisini görüntüler.

- **noreset** çalışma zamanı veri yapıları sayı korur.

*Görüntü*<br/>
Kullanılarak oluşturulan bir .exe veya .dll dosyasının tam yolu [/genprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), veya [/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md) seçeneği.

*pgcfile*<br/>
Bu komut verileri sayıları nereye yazdığını .pgc dosyası.

## <a name="remarks"></a>Açıklamalar

**Pgosweep** komutu kullanılarak oluşturulan programlar çalışır [/genprofıle veya fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) seçeneği veya kullanım dışı [/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md) seçeneği. Bu, çalışan bir program keser ve yeni bir .pgc dosyası için profil verileri yazar. Varsayılan olarak, komut sonra her yazma işlemi sayısını sıfırlar. Belirtirseniz **noreset** seçeneği, komut değerleri kaydedin ancak bunları sıfırlamak çalışan programa değil. Bu seçenek daha sonra profil verilerini alma, yinelenen verileri sağlar.

Alternatif bir kullanım için **pgosweep** yalnızca uygulamanın normal işlem için profil bilgilerini almak için. Örneğin, çalıştırabilirsiniz **pgosweep** kısa bir süre sonra uygulamayı başlatın ve bu dosyayı atmak sonra. Bu başlangıç maliyetleri ile ilişkili profil verilerini kaldırır. Daha sonra çalıştırabileceğiniz **pgosweep** uygulamayı sonlandırmadan önce. Artık toplanan verileri, kullanıcının programla destekliyordu profil bilgilerini yalnızca zamandan sahiptir.

.Pgc dosyası adı ne zaman (kullanarak *pgcfile* parametresi), standart biçiminde kullanabileceğiniz *appname! n*.pgc. Bu biçimi kullanırsanız, derleyici bu verileri otomatik olarak bulur. **/LTCG /USEPROFILE** veya **/LTCG:PGO** aşaması. Standart biçim kullanmazsanız kullanmalısınız [pgomgr](pgomgr.md) .pgc dosyaları birleştirmek için.

> [!NOTE]
> Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor.

Yürütülebilir dosyanın içindeki profili verileri yakalama hakkında daha fazla bilgi için bkz: [PgoAutoSweep](pgoautosweep.md).

## <a name="example"></a>Örnek

Bu örnek komutta **pgosweep** için myapp!1.pgc myapp.exe geçerli profil bilgilerini yazar.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
