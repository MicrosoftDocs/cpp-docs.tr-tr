---
title: 'Nasıl yapılır: Birden çok PGO profilini tek profilde birleştirme'
ms.date: 03/14/2018
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
ms.openlocfilehash: 451c0f30a271f5dce3974e172766da4a23340b93
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823674"
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Nasıl yapılır: Birden çok PGO profilini tek profilde birleştirme

Profil temelli iyileştirme (PGO), profil oluşturulan bir senaryoya göre en iyi duruma getirilmiş ikili dosyaları oluşturmak için harika bir araçtır. Ancak, birkaç önemli, henüz farklı senaryolar olan bir uygulama varsa ne olur? PGO kullanabileceğiniz tek bir profil birkaç farklı senaryolarından nasıl oluşturulur? Visual Studio'da PGO Manager [pgomgr.exe](pgomgr.md), bu işi sizin için yapar.

Profilleri birleştirme için sözdizimi aşağıdaki gibidir:

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

Burada `num` bu birleştirme tarafından eklenen .pgc dosyaları için kullanılacak isteğe bağlı bir ağırlık. Ağırlıklar, diğerlerinden daha önemli olan bazı senaryoları başladıysanız veya birden çok kez çalıştırılacak olan senaryoları başladıysanız yaygın olarak kullanılır.

> [!NOTE]
> PGO Yöneticisi eski profil verileri ile çalışmaz. .Pgc dosyası bir .pgd dosyası birleştirilecek .pgc dosyası .pgd dosyası oluşturulan aynı bağlantı çağrısı tarafından oluşturulan bir yürütülebilir dosya tarafından oluşturulmuş olması gerekir.

## <a name="examples"></a>Örnekler

Bu örnekte, PGO Manager pgcFile.pgc pgdFile.pgd için altı kat ekler:

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

Bu örnekte, PGO Manager pgcFile1.pgc ve pgcFile2.pgc pgdFile.pgd, iki kez için her .pgc dosyası ekler:

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

PGO Manager herhangi .pgc dosyası bağımsız değişkenler çalıştırırsanız, ardından bir ünlem işareti (!) ve ardından bir veya daha fazla rastgele karakterler .pgd dosyası olarak aynı temel ada sahip tüm .pgc dosyaları için yerel dizini arar. Örneğin, yerel dizin dosyaları test.pgd, test!1.pgc test2.pgc ve test!hello.pgc varsa ve şu komutu ardından yerel dizinden çalıştırın **pgomgr** test!1.pgc ve test!hello.pgc test.pgd birleştirir.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)
