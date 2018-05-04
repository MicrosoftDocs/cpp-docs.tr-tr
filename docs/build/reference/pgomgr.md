---
title: pgomgr | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf7567cfe9f21effda913606ca3af9a19464f9d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="pgomgr"></a>pgomgr

Profil verileri bir veya daha fazla .pgc dosyalarından .pgd dosyasına ekler.

## <a name="syntax"></a>Sözdizimi

> **pgomgr** [*seçenekleri*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
Aşağıdaki seçenekler için belirtilen **pgomgr**:

- **/ help** veya **/?** Görüntüler kullanılabilir **pgomgr** seçenekleri.

- **/ temizleyin** tüm profil bilgileri temizlenecek .pgd dosyasının neden olur. Bir .pgc belirtemezsiniz dosyası **/temizleyin** belirtilir.

- **/ Ayrıntı** akış grafiği kapsamı bilgiler dahil olmak üzere ayrıntılı istatistiklerini görüntüler.

- **/ Özet** görüntüler başına işlevi istatistikleri.

- **/ benzersiz** ile kullanıldığında **/Özet**, nedenleri görüntülemek için işlev adlarını donatılmış. Varsayılan değer, ne zaman **/ benzersiz** kullanılmaz, görüntülenecek ve işlev adları için değildir.

- **/ merge**[**: *** n*] .pgc dosya veya dosyalar .pgd dosyasına eklenecek veri neden olur. İsteğe bağlı bir parametre *n*, belirttiğiniz veri eklenmelidir sağlar *n* kez. Örneğin, bir senaryo genellikle müşteriler tarafından ne sıklıkta yapıldığını yansıtmak için Bitti'yi altı kat olacaktır, bir test çalıştırması kez yapın ve altı kat ile .pgd dosyasına ekleyin **pgomgr /merge:6**.

*pgcfiles*<br/>
Bir veya daha fazla .pgc .pgd dosyasına birleştirmek istediğiniz profili veri dosyaları. Bir tek .pgc dosya veya birden çok .pgc belirtebilirsiniz. Herhangi bir .pgc dosya belirtmezseniz, **pgomgr** , dosya adları .pgd dosya ile aynı olan tüm .pgc dosyaları birleştirir.

*pgdfile* içine, .pgc dosya veya dosyalar verileri .pgd dosya birleştirme.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut istemi veya dosya Gezgini başlatılamıyor.

## <a name="example"></a>Örnek

Bu örnek komut, profil verilerini myapp.pgd dosya temizler:

`pgomgr /clear myapp.pgd`

Bu örnek komut profil verileri myapp1.pgc içinde üç kez .pgd dosyasına ekler:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

Bu örnekte, tüm Uygulamam # .pgc dosyaları profil verileri myapp.pgd dosyasına eklenir.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
