---
title: pgosweep
description: Profil temelli iyileştirmede kullanılmak üzere bir PGC dosyasına profil verileri yazmak için pgosüpürme komutunu kullanın.
ms.date: 10/23/2020
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.openlocfilehash: be96d0f092ff65867c304ddf5eb41c0754f6e4be
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497187"
---
# <a name="pgosweep"></a>pgosweep

Çalışan bir programdaki tüm profil verilerini PGC dosyasına yazmak için profil temelli iyileştirme ' de kullanılır.

## <a name="syntax"></a>Syntax

> **`pgosweep`** [*Seçenekler*] *Image* *pgfile*

### <a name="parameters"></a>Parametreler

*Seçenekler*\
Seçim *Seçenekler* için geçerli değerler şunlardır:

- **`/?`** veya **`/help`** yardım iletisini görüntüler.

- **`/reset`** süpürme sonrasında sayıları sıfıra sıfırlar. Bu davranış varsayılandır.

- **`/pid:n`** yalnızca belirtilen PID 'ye sahip, burada *n* , PID numarasıdır.

- **`/wait`** sayıları toplamadan önce belirtilen PID 'nin sonlanacak şekilde bekler.

- **`/onlyzero`** PGC dosyası kaydetmez, yalnızca sıfır sayı sayılır.

- **`/pause`** sistemde Count toplamasını duraklatır.

- **`/resume`** sistemde Count toplamasını sürdürür.

- **`/noreset`** çalışma zamanı veri yapıları içindeki sayıyı korur.

*görüntüyle*\
[`/GENPROFILE`](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), Veya seçeneği kullanılarak oluşturulan BIR exe veya dll dosyasının tam yolu [`/FASTGENPROFILE`](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) [`/LTCG:PGINSTRUMENT`](reference/ltcg-link-time-code-generation.md) .

*pgfile*\
Bu komutun veri sayılarını yazdığı PGC dosyası.

## <a name="remarks"></a>Açıklamalar

**`pgosweep`** Komutu [ `/GENPROFILE` veya `/FASTGENPROFILE` ](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) seçeneği kullanılarak oluşturulan programlar veya kullanım dışı [`/LTCG:PGINSTRUMENT`](reference/ltcg-link-time-code-generation.md) seçeneği kullanılır. Çalışan bir programı keser ve profil verilerini yeni bir PGC dosyasına yazar. Varsayılan olarak, komut her yazma işleminden sonra sayıları sıfırlar. **`/noreset`** Seçeneğini belirtirseniz, komut değerleri kaydeder, ancak onları çalışan programda sıfırlayamaz. Bu seçenek, profil verilerini daha sonra alırsanız yinelenen verileri sağlar.

İçin alternatif bir kullanım **`pgosweep`** , uygulamanın normal işleminin yalnızca profil bilgilerini almadır. Örneğin, **`pgosweep`** Uygulamayı başlattıktan ve bu dosyayı atladıktan sonra kısa bir süre sonra çalıştırabilirsiniz. Bu komut, başlangıç maliyetleriyle ilişkili profil verilerini kaldırır. Ardından, **`pgosweep`** uygulamayı sonlandırmadan önce çalıştırabilirsiniz. Artık toplanan verilerin profil bilgileri, yalnızca kullanıcının programla etkileşime girebileceği zamandan itibaren yapılır.

Bir PGC dosyasını ( *pgfile* parametresini kullanarak) yazdığınızda, standart biçimini kullanabilirsiniz *`appname!n.pgc`* . *N* , her dosya için artan bir sayısal değeri temsil eder. Bu biçimi kullanırsanız, derleyici bu verileri veya aşamasında otomatik olarak bulur **`/LTCG /USEPROFILE`** **`/LTCG:PGO`** . Standart biçimi kullanmıyorsanız, [`pgomgr`](pgomgr.md) PGC dosyalarını birleştirmek için kullanmanız gerekir.

> [!NOTE]
> Bu aracı yalnızca bir Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız.

Yürütülebilir dosyanızın içinden profil verilerini yakalama hakkında daha fazla bilgi için bkz [`PgoAutoSweep`](pgoautosweep.md) ..

## <a name="example"></a>Örnek

Bu örnek komutunda, için **`pgosweep`** geçerli profil bilgilerini yazar *`myapp.exe`* *`myapp!1.pgc`* .

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>Ayrıca bkz.

[Profil temelli Iyileştirmeler](profile-guided-optimizations.md)\
[PgoAutoSweep](pgoautosweep.md)
