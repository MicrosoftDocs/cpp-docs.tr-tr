---
title: "Düşük düzey g-O | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.io
dev_langs: C++
helpviewer_keywords:
- I/O [CRT], low-level
- I/O [CRT], functions
- low-level I/O routines
- file handles [C++]
- file handles [C++], I/O functions
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cc923e8c638f51720aaffbb8c26aaa65bb230731
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="low-level-io"></a>Düşük Düzey G/Ç
Bu işlevler işletim sistemi akış g/ç tarafından sağlanan daha düşük düzeyli işlemi için doğrudan çağırma. Alt düzey giriş ve çıkış çağrı yapmak arabellek veya biçim verileri değil.  
  
 Alt düzey yordamları aşağıdaki önceden tanımlanmış dosya tanımlayıcıları kullanarak programı başlangıçta açılan standart akışlarına erişebilir.  
  
|Akış|Dosya tanımlayıcısı|  
|------------|---------------------|  
|`stdin`|0|  
|`stdout`|1.|  
|`stderr`|2|  
  
 Düşük düzey g/ç yordamları kümesi [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bir hata oluştuğunda genel değişkeni. STDIO eklemeniz gerekir. Yalnızca programınız STDIO içinde tanımlanan bir sabit gerektiriyorsa, alt düzey işlevleri kullandığınızda H. Dosya sonu göstergesi gibi H (`EOF`).  
  
### <a name="low-level-io-functions"></a>Düşük düzey g/ç işlevleri  
  
|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|---------|  
|[_close](../c-runtime-library/reference/close.md)|Dosyayı Kapat|  
|[_commit](../c-runtime-library/reference/commit.md)|Disk temizleme dosyasına|  
|[_creat, _wcreat](../c-runtime-library/reference/creat-wcreat.md)|Dosya Oluştur|  
|[_dup](../c-runtime-library/reference/dup-dup2.md)|Dosya için dönüş sonraki kullanılabilir dosya tanımlayıcısı verilen|  
|[_dup2](../c-runtime-library/reference/dup-dup2.md)|Belirtilen ikinci tanımlayıcısı oluşturun dosyası|  
|[_eof](../c-runtime-library/reference/eof.md)|Dosya sonu için test etme|  
|[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Yeniden konumlandırma dosya işaretçisini konumu verilen|  
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|dosyasını açın|  
|[_read](../c-runtime-library/reference/read.md)|Veri dosyasından okuma|  
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Dosya Paylaşımı için Dosya Aç|  
|[_tell, _telli64](../c-runtime-library/reference/tell-telli64.md)|Geçerli dosya işaretçisini konumu Al|  
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Dosya izni maske ayarlama|  
|[_write](../c-runtime-library/reference/write.md)|Veri dosyasına yazma|  
  
 `_dup`ve `_dup2` genellikle önceden tanımlanmış dosya tanımlayıcıları farklı dosyaları ile ilişkilendirmek için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş ve çıkış](../c-runtime-library/input-and-output.md)   
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)   
 [Sistem Çağrıları](../c-runtime-library/system-calls.md)