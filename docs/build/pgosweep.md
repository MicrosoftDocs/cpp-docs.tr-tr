---
title: pgosweep
ms.date: 03/14/2018
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
ms.openlocfilehash: 3ba31671fc3794e1cc959d86d914ba1eef2e01e4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824023"
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
Kullanılarak oluşturulan bir .exe veya .dll dosyasının tam yolu [/genprofıle](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [fastgenprofıle](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), veya [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) seçeneği.

*pgcfile*<br/>
Bu komut verileri sayıları nereye yazdığını .pgc dosyası.

## <a name="remarks"></a>Açıklamalar

**Pgosweep** komutu kullanılarak oluşturulan programlar çalışır [/genprofıle veya fastgenprofıle](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) seçeneği veya kullanım dışı [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) seçeneği. Bu, çalışan bir program keser ve yeni bir .pgc dosyası için profil verileri yazar. Varsayılan olarak, komut sonra her yazma işlemi sayısını sıfırlar. Belirtirseniz **noreset** seçeneği, komut değerleri kaydedin ancak bunları sıfırlamak çalışan programa değil. Bu seçenek daha sonra profil verilerini alma, yinelenen verileri sağlar.

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
