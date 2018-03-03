---
title: pgosweep | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78ae6c36011e3c10359988cf2c501514d1bcf70a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pgosweep"></a>pgosweep
Profil temelli iyileştirme tüm profil verilerini çalışan bir programı .pgc dosyaya yazmak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### <a name="parameters"></a>Parametreler  
 `options`  
 Boş bırakılabilir isteğe bağlı bir parametre. İçin geçerli değerleri `options` aşağıdaki gibidir:  
  
-   **/?** veya **/Help,** Yardım iletisi görüntüler.  
  
-   **/noreset,** çalışma zamanı veri yapılarını sayıma korur.  
  
 `image`  
 Derleyici seçeneği /LTCG:PGINSTRUMENT kullanılarak oluşturulmuş bir .exe veya .dll dosyasının tam yolu.  
  
 `pgcfile`  
 Bu komutu sayımları verileri nerede yazacak .pgc dosyası.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu komut /LTCG:PGINSTRUMENT derleyici seçeneği ile oluşturulan programlar çalışır. Çalışan bir program keser ve profil verileri yeni bir .pgc dosyaya yazar. Varsayılan olarak, komutu sayımları sonra her yazma işlemi sıfırlar. Belirtirseniz **/noreset** seçeneğini komutu kayıt değerlerine ancak bunları çalışan programa sıfırlama. Profil verileri daha sonra alırsanız, bu seçenek yinelenen verileri verir.  
  
 İçin alternatif kullanımınız `pgosweep` uygulamanın yalnızca çalışma zamanı için profil bilgilerini almak için. Örneğin, çalıştırabilirsiniz `pgosweep` kısa bir süre sonra uygulamayı başlatmak ve bu dosyayı atmak sonra. Bu başlangıç maliyetleri ile ilişkili profil verilerini kaldırabilirsiniz. Daha sonra çalıştırabilirsiniz `pgosweep` uygulama sonlandırmadan önce. Artık toplanan verileri profili bilgileri yalnızca çalışma zamanı sahiptir.  
  
 .Pgc dosya adı zaman (`pgcfile`), standart biçiminde kullanabilirsiniz *appname! n*.pgc. Bu biçimi kullanıyorsanız, derleyici /LTCG:PGO aşamasında bu verileri bulur. Standart biçim kullanmazsanız, kullanmalısınız [pgomgr](../../build/reference/pgomgr.md) .pgc dosyaları birleştirmek için.  
  
## <a name="example"></a>Örnek  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 Bu örnekte, `pgosweep` için myapp!1.pgc myapp.exe geçerli profil bilgilerini yazar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [El ile Profil Temelli İyileştirme Araçları](../../build/reference/tools-for-manual-profile-guided-optimization.md)