---
title: pgomgr
ms.date: 03/14/2018
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
ms.openlocfilehash: 4e3eb08c88db9d0ed4e47649014a600c3e0ccb78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540510"
---
# <a name="pgomgr"></a>pgomgr

Profil verileri, bir veya daha fazla .pgc dosyaları için .pgd dosyası ekler.

## <a name="syntax"></a>Sözdizimi

> **pgomgr** [*seçenekleri*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
Aşağıdaki seçenekler için belirtilebilir **pgomgr**:

- **/ help** veya **/?** Kullanılabilir görüntüler **pgomgr** seçenekleri.

- **/ clear** tüm profil bilgilerinin temizlenmesi için .pgd dosyasını neden olur. Bir .pgc belirtemezsiniz dosyası **/clear** belirtilir.

- **/ detail** akış grafiği kapsamı bilgileri dahil olmak üzere ayrıntılı istatistiklerini görüntüler.

- **/ summary** görüntüler işlev başına istatistikleri.

- **/ benzersiz** ile kullanıldığında **/summary**, donatılmış işlev adlarını görüntülemek için neden olur. Varsayılan, **/ benzersiz** kullanılmaz, görüntülenecek ve işlev adları için.

- **/ merge**\[**:**<em>n</em>] .pgc dosya veya dosyalar için .pgd dosyası eklenecek veri neden olur. İsteğe bağlı parametre *n*, belirttiğiniz veri eklenmelidir sağlar *n* kez. Örneğin, bir senaryo müşteriler tarafından ne sıklıkta yapıldığını yansıtacak şekilde sık yapılan altı kat olacaktır, bir test çalıştırmasında bir kez yapın ve altı kat ile .pgd dosyası eklemek **pgomgr /merge:6**.

*pgcfiles*<br/>
.Pgd dosyası birleştirmek istediğiniz profil verisini bir veya daha fazla .pgc dosyaları. Tek .pgc dosyası veya birden çok .pgc dosyaları belirtebilirsiniz. Herhangi bir .pgc dosyası belirtmezseniz **pgomgr** olan dosya adlarını .pgd dosyası ile aynı olan tüm .pgc dosyaları birleştirir.

*pgdfile*<br/>
.Pgd dosyası içine .pgc dosyası veya dosya verilerini birleştirme.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor.

## <a name="example"></a>Örnek

Bu örnek komut myapp.pgd dosya, profil verilerini siler:

`pgomgr /clear myapp.pgd`

Bu örnek komut profil verileri myapp1.pgc içinde üç kez için .pgd dosyası ekler:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

Bu örnekte, myapp # .pgc dosyalarından tüm profil verilerini myapp.pgd dosyasına eklenir.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
