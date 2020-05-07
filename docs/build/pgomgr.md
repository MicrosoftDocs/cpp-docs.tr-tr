---
title: pgomgr
ms.date: 03/14/2018
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
ms.openlocfilehash: 4e3eb08c88db9d0ed4e47649014a600c3e0ccb78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295259"
---
# <a name="pgomgr"></a>pgomgr

Profil verilerini bir veya daha fazla. pgc dosyasından. pgd dosyasına ekler.

## <a name="syntax"></a>Sözdizimi

> **Pgomgr** [*Seçenekler*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
**Pgomgr**için aşağıdaki seçenekler belirlenebilir:

- **/help** veya **/?** Kullanılabilir **Pgomgr** seçeneklerini görüntüler.

- **/clear** . Pgd dosyasının tüm profil bilgileri temizlenmesine neden olur. **/Clear** belirtildiğinde bir. pgc dosyası belirtemezsiniz.

- **/detail** Akış grafiği kapsam bilgileri de dahil olmak üzere ayrıntılı istatistikleri görüntüler.

- **/Summary** İşlev başına istatistikleri görüntüler.

- **/Unique** **/Summary**ile kullanıldığında, düzenlenmiş işlev adlarının görüntülenmesine neden olur. Varsayılan, **/Unique** kullanılmazsa, açıklanmayan işlev adlarının gösterilmesi içindir.

- **/Merge**\[**:**<em>n</em>]. pgc dosyasındaki veya dosyalardaki verilerin. pgd dosyasına eklenmesine neden olur. İsteğe bağlı *n*parametresi, verilerin *n* kez ekleneceğini belirtmenize olanak tanır. Örneğin, bir senaryo, müşteriler tarafından ne sıklıkla yapıldığını yansıtmak için genellikle altı kez yapılacağından, Test çalıştırmasında bir kez bunu yapabilir ve bunu **Pgomgr/merge: 6**ile altı kez. pgd dosyasına ekleyebilirsiniz.

*pgcfiles*<br/>
Profil verilerini. pgd dosyasında birleştirmek istediğiniz bir veya daha fazla. pgc dosyası. Tek bir. pgc dosyası veya birden çok. pgc dosyası belirtebilirsiniz. Herhangi bir. pgc dosyası belirtmezseniz, **Pgomgr** , dosya adları. pgd dosyasıyla aynı olan tüm. pgc dosyalarını birleştirir.

*pgdfile*<br/>
. Pgc dosyası veya dosyalarından verileri birleştirdiğiniz. pgd dosyası.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu aracı yalnızca bir Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bunu bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız.

## <a name="example"></a>Örnek

Bu örnek komut, profil verilerinin MyApp. pgd dosyasını temizler:

`pgomgr /clear myapp.pgd`

Bu örnek komut, Myapp1. pgc içindeki profil verilerini. pgd dosyasına üç kez ekler:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

Bu örnekte, tüm MyApp #. pgc dosyalarındaki profil verileri MyApp. pgd dosyasına eklenir.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
