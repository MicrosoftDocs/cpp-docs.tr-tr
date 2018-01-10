---
title: pgomgr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cbb9a4f8b92a1cd495e1312c1aa8a8f77cefcd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pgomgr"></a>pgomgr
Profil verileri bir veya daha fazla .pgc dosyalarından .pgd dosyasına ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### <a name="parameters"></a>Parametreler  
 `options`  
 Aşağıdaki seçenekler için pgomgr belirtilebilir:  
  
 **/ help —**kullanılabilir pgomgr seçenekleri görüntüler (kısa için /?).  
  
 **/ temizleyin —**tüm profil bilgileri temizlenecek .pgd dosyasının neden olur. Bir .pgc belirtemezsiniz dosyası **/temizleyin** belirtilir.  
  
 **/ Ayrıntı**— akış grafiği kapsamı bilgiler dahil olmak üzere ayrıntılı istatistiklerini görüntüler.  
  
 **/ Özet**— görüntüler başına işlevi istatistikleri.  
  
 **/ benzersiz**— kullanıldığında **/Özet**, nedenleri görüntülemek için işlev adlarını donatılmış.  Varsayılan, benzersiz olduğu değil, görüntülenecek ve işlev adları için kullanılır.  
  
 **/ merge**[**:***n*]**—**.pgc dosya veya dosyalar .pgd dosyasına eklenecek veri neden olur.  İsteğe bağlı bir parametre  *n* , belirttiğiniz hat veri eklenmesi sağlar  *n*  kez.  Örneğin, bir senaryo 6 kereye yaygın olarak uygulanır, bir test çalıştırması kez yapın ve altı kat ile .pgd dosyasına ekleyin **pgomgr /merge:6**.  
  
 `pgcfiles`  
 Bir veya daha fazla .pgc .pgd dosyasına birleştirmek istediğiniz profili veri dosyaları. Bir tek .pgc dosya veya birden çok .pgc belirtebilirsiniz. Herhangi bir .pgc dosyası belirtmezseniz, pgomgr .pgd dosyası ile aynı olan dosya adları olan tüm .pgc dosyaları birleştirme.  
  
 `pgdfile`  
 İçine .pgc dosya veya dosyalar verileri birleştirme .pgd dosyası.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu araç yalnızca başlatabilirsiniz [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] komut istemi. Bir sistem komut istemi veya dosya Gezgini başlatılamıyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, .pgd dosyası profil verileri temizlendi.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 Aşağıdaki örnekte, myapp1.pgc profil verileri 3 kez .pgd dosyasına eklendi.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 Aşağıdaki örnekte, tüm Uygulamam # .pgc dosyaları profil verileri myapp.pgd dosyasına eklenir.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [El ile Profil Temelli İyileştirme Araçları](../../build/reference/tools-for-manual-profile-guided-optimization.md)