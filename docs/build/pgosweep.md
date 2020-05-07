---
title: pgosweep
ms.date: 03/14/2018
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
ms.openlocfilehash: 3ba31671fc3794e1cc959d86d914ba1eef2e01e4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341193"
---
# <a name="pgosweep"></a>pgosweep

Çalışan bir programdan. pgc dosyasına tüm profil verilerini yazmak için profil temelli iyileştirme ' de kullanılır.

## <a name="syntax"></a>Sözdizimi

> **pgosüpürme** [*Options*] *Image* *pgfile*

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
Seçim *Seçenekler* için geçerli değerler şunlardır:

- **/?** veya **/help** yardım iletisini görüntüler.

- **/NORESET süpürmeden** , çalışma zamanı veri yapıları içindeki sayıyı korur.

*görüntüyle*<br/>
[/GENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/fastgenprofile](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)veya [/LTCG: PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) seçeneği kullanılarak oluşturulan bir. exe veya. dll dosyasının tam yolu.

*pgfile*<br/>
Bu komutun veri sayılarını yazdığı. pgc dosyası.

## <a name="remarks"></a>Açıklamalar

**Pgogereçme** komutu [/GENPROFILE veya/fastgenprofile](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) seçeneği kullanılarak oluşturulan programlarda veya kullanım DıŞı [/LTCG: PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) seçeneğiyle birlikte kullanılabilir. Çalışan bir programı keser ve profil verilerini yeni bir. pgc dosyasına yazar. Varsayılan olarak, komut her yazma işleminden sonra sayıları sıfırlar. **/NORESET süpürmeden** seçeneğini belirtirseniz, komut değerleri kaydeder, ancak onları çalışan programda sıfırlayamaz. Bu seçenek, profil verilerini daha sonra alırsanız yinelenen verileri sağlar.

**Pgosüpürme** için alternatif bir kullanım, yalnızca uygulamanın normal işlemleri için profil bilgilerini almak içindir. Örneğin, uygulamayı başlattıktan ve bu dosyayı atladıktan sonra kısa bir süre sonra **pgosüpürme** çalıştırabilirsiniz. Bu, başlangıç maliyetleriyle ilişkili profil verilerini kaldırır. Ardından, uygulamayı sonlandırmadan önce **pgosüpürme** çalıştırabilirsiniz. Artık toplanan verilerin profil bilgileri, yalnızca kullanıcının programla etkileşime girebileceği zamandan itibaren yapılır.

Bir. pgc dosyasını ( *pgfile* parametresini kullanarak) belirlediğinizde, *appname! n*. pgc olan standart biçimini kullanabilirsiniz. Bu biçimi kullanırsanız, derleyici bu verileri **/LTCG/USEPROFıLE** veya **/LTCG: PGO** aşamasında otomatik olarak bulur. Standart biçimi kullanmıyorsanız,. pgc dosyalarını birleştirmek için [Pgomgr](pgomgr.md) kullanmanız gerekir.

> [!NOTE]
> Bu aracı yalnızca bir Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bunu bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız.

Yürütülebilir dosyanızın içinden profil verilerini yakalama hakkında daha fazla bilgi için bkz. [Pgooto süpürme](pgoautosweep.md).

## <a name="example"></a>Örnek

Bu örnek komutta, **pgosüpürme** , MyApp. exe için geçerli profil bilgilerini MyApp! 1. pgc öğesine yazar.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
