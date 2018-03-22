---
title: pgosweep | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9680dc47d850bd49eff343c0e382b7132697858d
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="pgosweep"></a>pgosweep

Profil temelli iyileştirme tüm profil verilerini çalışan bir programı .pgc dosyaya yazmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **pgosweep** [*seçenekleri*] *görüntü* *pgcfile*

### <a name="parameters"></a>Parametreler

*Seçenekler* (isteğe bağlı)<br/>
İçin geçerli değerleri *seçenekleri* şunlardır:

- **/?** veya **/Yardım** Yardım iletisi görüntüler.

- **/noreset** çalışma zamanı veri yapılarını sayıma korur.

*image*<br/>
Kullanılarak oluşturulmuş bir .exe veya .dll dosyasının tam yolu [/GENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), veya [/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md) seçeneği.

*pgcfile*<br/>
Burada bu komutu sayımları verileri yazar .pgc dosyası.

## <a name="remarks"></a>Açıklamalar

**Pgosweep** komutu çalışır kullanılarak oluşturulmuş programları [/GENPROFILE veya /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) seçeneği veya kullanım dışı [/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md) seçeneği. Çalışan bir program keser ve profil verileri yeni bir .pgc dosyaya yazar. Varsayılan olarak, komutu sayımları sonra her yazma işlemi sıfırlar. Belirtirseniz **/noreset** seçeneğini komutu kayıt değerlerine ancak bunları çalışan programa sıfırlama. Profil verileri daha sonra alırsanız bu seçenek, yinelenen verileri sağlar.

Alternatif kullanımınız için **pgosweep** yalnızca uygulamanın normal işlem için profil bilgilerini almak için. Örneğin, çalıştırabilirsiniz **pgosweep** kısa bir süre sonra uygulamayı başlatmak ve bu dosyayı atmak sonra. Bu başlangıç maliyetleri ile ilişkili profil verilerini kaldırabilirsiniz. Daha sonra çalıştırabilirsiniz **pgosweep** uygulama sonlandırmadan önce. Artık toplanan veriler, kullanıcının programla destekliyordu profili bilgileri yalnızca zamandan sahiptir.

.Pgc dosya adı zaman (kullanarak *pgcfile* parametresi), standart biçiminde kullanabilirsiniz *appname! n*.pgc. Bu biçimi kullanıyorsanız, bu verileri derleyici otomatik olarak bulur. **/LTCG /USEPROFILE** veya **/LTCG:PGO** aşaması. Standart biçim kullanmazsanız, kullanmalısınız [pgomgr](pgomgr.md) .pgc dosyaları birleştirmek için.

> [!NOTE]
> Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut istemi veya dosya Gezgini başlatılamıyor.

Yürütülebilir dosyanın içindeki profil verileri yakalama hakkında daha fazla bilgi için bkz: [PgoAutoSweep](pgoautosweep.md).

## <a name="example"></a>Örnek

Bu örnek komutta **pgosweep** myapp!1.pgc için myapp.exe geçerli profil bilgilerini yazar.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
