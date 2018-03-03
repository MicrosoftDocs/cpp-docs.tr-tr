---
title: "Dosya işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.files
dev_langs:
- C++
helpviewer_keywords:
- files [C++], handling
- files [C++], opening
- files [C++], manipulating
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 129267c69a2cf4830587f8ebc7c445a01591235b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="file-handling"></a>Dosya İşleme
Oluşturma, silme ve dosyaları yönetmek için ve ayarlama ve dosya erişim izinlerini denetlemek için bu yordamları kullanın.  
  
 C çalışma zamanı kitaplıkları herhangi bir zamanda açık dosya sayısı için 512 sınırlaması vardır. En yüksek sayısını dosya tanımlayıcıları veya dosya akışları program hatasına neden olur. fazlasını açılmaya çalışılıyor. Kullanım [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) bu numarasını değiştirmek için.  
  
### <a name="file-handling-routines-file-descriptor"></a>Dosya işleme rutinleri (dosya tanımlayıcısı)  
  
 Bu yordamlar, dosya tanımlayıcısı tarafından belirtilen dosyalar üzerinde çalışır.  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[_chsize](../c-runtime-library/reference/chsize.md),[_chsize_s](../c-runtime-library/reference/chsize-s.md)|Dosya boyutunu değiştirme|  
|[_filelength, _filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Dosya uzunluğu alma|  
|[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Dosya durumu tanımlayıcısı hakkında bilgi edinin|  
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Varolan C çalışma zamanı dosya tanımlayıcısıyla ilişkilendirilen dönüş işletim sistemi dosya işleci|  
|[_isatty](../c-runtime-library/reference/isatty.md)|Karakter cihazı denetleme|  
|[_locking](../c-runtime-library/reference/locking.md)|Dosya kilitleme alanları|  
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C çalışma zamanı dosya tanımlayıcısı varolan işletim sistemi dosya işleci ile ilişkilendirme|  
|[_setmode](../c-runtime-library/reference/setmode.md)|Dosya çevirisi modunu ayarlama|  
  
### <a name="file-handling-routines-path-or-filename"></a>Dosya işleme rutinleri (yol veya dosya adı)  
  
 Bu yordamlar, bir yol veya dosya adı tarafından belirtilen dosyalar üzerinde işlem yapar.  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[_access, _waccess](../c-runtime-library/reference/access-waccess.md), [_access_s, _waccess_s](../c-runtime-library/reference/access-s-waccess-s.md)|Dosya izni ayarı denetleyin|  
|[_chmod, _wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Dosya izni ayarı Değiştir|  
|[_fullpath, _wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Göreli bir yol mutlak bir yol adını genişletin|  
|[_makepath, _wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [_makepath_s, _wmakepath_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Yol bileşenlerini tek, tam yola birleştirme|  
|[_mktemp, _wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [_mktemp_s, _wmktemp_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Benzersiz dosya adı oluşturun|  
|[remove, _wremove](../c-runtime-library/reference/remove-wremove.md)|Dosya Sil|  
|[rename, _wrename](../c-runtime-library/reference/rename-wrename.md)|Dosyayı yeniden adlandırın|  
|[_splitpath, _wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [_splitpath_s, _wsplitpath_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Bileşenlerine yolu ayrıştırılamıyor|  
|[_stat, _stat64, _stati64, _wstat, _wstat64, _wstati64](../c-runtime-library/reference/stat-functions.md)|Adlı dosyada dosya durum bilgilerini alma|  
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Program tarafından oluşturulan yeni dosyalar için varsayılan izni maskesini ayarlama|  
|[_unlink, _wunlink](../c-runtime-library/reference/unlink-wunlink.md)|Dosya Sil|  
  
### <a name="file-handling-routines-open-file"></a>Dosya işleme rutinleri (açık dosyası)  
  
 Bu yordamlar dosyalarını açın.  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Bir dosyayı açar ve açık olan dosyaya bir işaretçi döndürür.|  
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Dosya Paylaşımı ile bir akış açın ve açık olan dosyaya bir işaretçi döndürür.|  
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Bir dosyayı açar ve bir dosya tanımlayıcısı açılan dosyayı döndürür.|  
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Dosya Paylaşımı ile bir dosya açın ve açık dosyanın dosya tanımlayıcısı döndürür.|  
|[_pipe](../c-runtime-library/reference/pipe.md)|Okuma ve yazma için bir kanal oluşturur.|  
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Dosya işaretçisini yeniden atayın.|  
  
 Bu yordamlar arasında dosya gösterimini değiştirmek için bir yol sağlayan bir `FILE` yapısı, bir dosya tanımlayıcısı ve bir Win32 dosya işleci.  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Düşük düzey g/ç için daha önce açıldı ve açık akışa işaretçi döndüren bir dosya akışı ilişkilendirir.|  
|[_fileno](../c-runtime-library/reference/fileno.md)|Bir akış ile ilişkili dosya tanımlayıcısı alır.|  
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Varolan C çalışma zamanı dosya tanımlayıcısıyla ilişkilendirilen dönüş işletim sistemi dosya işleci|  
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C çalışma zamanı dosya tanımlayıcısı var olan bir işletim sistemi dosya tanıtıcısı ile ilişkilendirir.|  
  
 Aşağıdaki Win32 işlevleri de dosyaları ve kanallar açın:  
  
-   [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858.aspx)  
  
-   [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)  
  
-   [CreateNamedPipe](http://msdn.microsoft.com/library/windows/desktop/aa365150.aspx)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)   
 [Dizin denetimi](../c-runtime-library/directory-control.md)   
 [Sistem Çağrıları](../c-runtime-library/system-calls.md)