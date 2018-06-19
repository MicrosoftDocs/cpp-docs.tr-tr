---
title: 'Nasıl yapılır: birden çok PGO profilini tek profilde birleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca8fd6ef94af290d568f3186747c659b918c0fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372288"
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Nasıl Yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme

Profil temelli iyileştirme (PGO) profili bir senaryoyu temel en iyi duruma getirilmiş ikili dosyaları oluşturmak için harika bir araçtır. Ancak, çeşitli önemli, henüz farklı senaryolar olan bir uygulama yoksa ne? PGO kullanabilirsiniz tek bir profil birkaç farklı senaryolarından oluşturma? Visual Studio'da PGO Yöneticisi'ni [pgomgr.exe](pgomgr.md), olmadığından bu işlem sizin için.

Profilleri birleştirme için sözdizimi aşağıdaki gibidir:

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

Burada `num` bu birleştirme tarafından eklenen .pgc dosyalar için kullanılacak isteğe bağlı bir ağırlık. Ağırlıkları diğerlerinden daha önemli bazı senaryolar varsa veya birden çok kez çalıştırılacak senaryoları ise yaygın olarak kullanılır.

> [!NOTE]
> PGO Yöneticisi eski profil verileri ile çalışmaz. .Pgc dosya .pgd dosyasına birleştirmek için .pgc dosya .pgd dosya oluşturulan bir aynı bağlantı çağrı tarafından oluşturulan bir yürütülebilir dosya tarafından oluşturulmuş olması gerekir.

## <a name="examples"></a>Örnekler

Bu örnekte, altı kat için pgdFile.pgd pgcFile.pgc PGO Yöneticisi'ni ekler:

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

Bu örnekte, iki kez her .pgc dosyası için pgdFile.pgd için pgcFile1.pgc ve pgcFile2.pgc PGO Yöneticisi'ni ekler:

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

PGO Yöneticisi'ni herhangi .pgc dosya bağımsız değişkenler çalıştırırsanız, ardından bir ünlem işareti (!) ve ardından bir veya daha fazla rastgele karakterler .pgd dosyası olarak aynı taban adına sahip tüm .pgc dosyaların yerel dizinini arar. Örneğin, yerel dizin dosyaları test.pgd, test!1.pgc, test2.pgc ve test!hello.pgc varsa ve aşağıdaki komutu sonra yerel bir dizinden şunu çalıştırın **pgomgr** test!1.pgc ve test!hello.pgc test.pgd birleştirir.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)
