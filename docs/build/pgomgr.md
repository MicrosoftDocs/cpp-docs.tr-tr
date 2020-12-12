---
description: 'Daha fazla bilgi edinin: pgomgr'
title: pgomgr
ms.date: 03/14/2018
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
ms.openlocfilehash: 3b6b969becde43b98ea06f2058dd235eaf0acbed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187357"
---
# <a name="pgomgr"></a>pgomgr

Profil verilerini bir veya daha fazla. pgc dosyasından. pgd dosyasına ekler.

## <a name="syntax"></a>Syntax

> **Pgomgr** [*Seçenekler*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
**Pgomgr** için aşağıdaki seçenekler belirlenebilir:

- **/help** veya **/?** Kullanılabilir **Pgomgr** seçeneklerini görüntüler.

- **/clear** . Pgd dosyasının tüm profil bilgileri temizlenmesine neden olur. **/Clear** belirtildiğinde bir. pgc dosyası belirtemezsiniz.

- **/detail** Akış grafiği kapsam bilgileri de dahil olmak üzere ayrıntılı istatistikleri görüntüler.

- **/Summary** İşlev başına istatistikleri görüntüler.

- **/Unique** **/Summary** ile kullanıldığında, düzenlenmiş işlev adlarının görüntülenmesine neden olur. Varsayılan, **/Unique** kullanılmazsa, açıklanmayan işlev adlarının gösterilmesi içindir.

- **/merge** \[ **:**<em>n</em>]. pgc dosyasındaki veya dosyalardaki verilerin. pgd dosyasına eklenmesine neden olur. İsteğe bağlı *n* parametresi, verilerin *n* kez ekleneceğini belirtmenize olanak tanır. Örneğin, bir senaryo, müşteriler tarafından ne sıklıkla yapıldığını yansıtmak için genellikle altı kez yapılacağından, Test çalıştırmasında bir kez bunu yapabilir ve bunu **Pgomgr/merge: 6** ile altı kez. pgd dosyasına ekleyebilirsiniz.

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

[Profil temelli Iyileştirmeler](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
