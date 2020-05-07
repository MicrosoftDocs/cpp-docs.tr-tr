---
title: 'Nasıl Yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme'
ms.date: 03/14/2018
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
ms.openlocfilehash: 451c0f30a271f5dce3974e172766da4a23340b93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188879"
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Nasıl Yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme

Profil temelli iyileştirme (PGO), profili oluşturulmuş bir senaryoya bağlı olarak iyileştirilmiş ikililer oluşturmaya yönelik harika bir araçtır. Ancak birkaç önemli, ancak farklı senaryolar içeren bir uygulamanız varsa ne olacak? PGO 'nun birkaç farklı senaryodan kullanabileceği tek bir profil nasıl oluşturulur? Visual Studio 'da PGO Yöneticisi olan [pgomgr. exe](pgomgr.md), bu işi sizin için yapar.

Profillerin birleştirilmesi için sözdizimi şöyledir:

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

Burada `num` , bu birleştirme tarafından eklenen. pgc dosyaları için kullanılacak isteğe bağlı bir ağırlık vardır. Ağırlıklarla daha önemli olan bazı senaryolar varsa veya birden çok kez çalıştırılacak senaryolar varsa, ağırlıklar yaygın olarak kullanılır.

> [!NOTE]
> PGO Yöneticisi eski profil verileriyle çalışmaz. . Pgc dosyasını bir. pgd dosyasına birleştirmek için. pgc dosyası. pgd dosyasını oluşturan aynı bağlantı çağrısı tarafından oluşturulan bir yürütülebilir dosya tarafından oluşturulmalıdır.

## <a name="examples"></a>Örnekler

Bu örnekte, PGO Yöneticisi pgcFile. pgc öğesini pgdFile. pgd altı kez ekler:

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

Bu örnekte, PGO Yöneticisi, her. pgc dosyası için iki kez pgcFile1. pgc ve pgcFile2. pgc öğesini pgdFile. pgd öğesine ekler:

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

PGO Yöneticisi herhangi bir. PGC dosya bağımsız değişkeni olmadan çalışıyorsa,. pgd dosyası ile aynı temel ada sahip tüm. pgc dosyaları için yerel dizinde, ardından bir ünlem işareti (!) ve ardından bir veya daha fazla rastgele karakter arar. Örneğin, yerel dizinde test. pgd, test! 1. pgc, Test2. pgc ve test! Merhaba. pgc dosyaları varsa ve aşağıdaki komut yerel dizinden çalıştırılmışsa, **Pgomgr** testi! 1. pgc ve test! Merhaba. pgc öğesini test. pgd içine birleştirir.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)
