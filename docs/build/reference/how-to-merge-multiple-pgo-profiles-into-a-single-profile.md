---
title: "Nasıl yapılır: birden çok PGO profilini tek profilde birleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 880e9fbba7852a9a7919e73f80b73e34394cd037
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Nasıl Yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme
Profil temelli iyileştirme (PGO) profili bir senaryoyu temel en iyi duruma getirilmiş ikili dosyaları oluşturmak için harika bir araçtır. Ancak, bir uygulama yoksa ne birkaç önemli, henüz farklı senaryolar sahip; PGO kullanabilirsiniz tek bir profil birkaç farklı senaryolarından oluşturma? Visual Studio'da PGO Yöneticisi, Pgomgr.exe, bu işlemi sizin için yapar.  
  
 Profilleri birleştirme için sözdizimi aşağıdaki gibidir:  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 Burada `num` bu birleştirme için kullanılan isteğe bağlı bir ağırlık. Ağırlıkları diğerlerinden daha önemli bazı senaryolar varsa veya birden çok kez çalıştırılacak senaryoları ise yaygın olarak kullanılır.  
  
> [!NOTE]
>  PGO Yöneticisi eski profil verileri ile çalışmaz. .Pgc dosya .pgd dosyasına birleştirmek için .pgc dosya .pgd dosya oluşturulan bir aynı bağlantı çağrı tarafından oluşturulan bir yürütülebilir dosya tarafından oluşturulmuş olması gerekir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, PGO Manager pgcFile.pgc pgdFile.pgd için altı kat ekler.  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte, PGO Yöneticisi'ni pgcFile1.pgc ve pgcFile2.pgc iki kez her .pgc dosyası için pgdFile.pgd ekleyeceksiniz.  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Örnek  
 PGO Yöneticisi'ni .pgc dosyası çalıştırırsanız ünlem rasgele karakterle devam etmelidir (!) eklenmiş .pgd dosyasıyla aynı ada sahip tüm .pgc dosyaların yerel dizinini arar. Yerel dizindeki dosyaları test.pgd, test!1.pgc, test2.pgc ve test!hello.pgc varsa ve yerel dizininden aşağıdaki komutu çalıştırın, ardından test!1.pgc ve test!hello.pgc test.pgd birleştirilir.  
  
```  
pgomgr /merge test.pgd  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)