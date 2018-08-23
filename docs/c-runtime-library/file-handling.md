---
title: Dosya işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.files
dev_langs:
- C++
helpviewer_keywords:
- files [C++], handling
- files [C++], opening
- files [C++], manipulating
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f766aa4df157fdb4b422ea8143be11e91621e2
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42465189"
---
# <a name="file-handling"></a>Dosya İşleme

Oluşturma, silme ve dosyaları işleme ayarlayın ve dosya erişim izinlerini denetlemek için bu yordamları kullanın.

C çalışma zamanı kitaplıkları için herhangi bir zamanda açık dosyaların sayısı, 512 sınırlaması vardır. Daha fazla dosya tanımlayıcıları veya dosya akışları sayısı program hatalarına neden olan açık çalışılıyor. Kullanım [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) bu sayıyı değiştirmek için.

## <a name="file-handling-routines-file-descriptor"></a>Dosya işleme rutinleri (dosya tanımlayıcısı)

Bu yordamların bir dosya tanımlayıcısı tarafından belirtilen dosyalar üzerinde çalışır.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_chsize](../c-runtime-library/reference/chsize.md),[_chsize_s](../c-runtime-library/reference/chsize-s.md)|Dosya boyutunu değiştirme|
|[_filelength, _filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Dosya uzunluğu alma|
|[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Tanımlayıcı üzerinde dosya durumu bilgilerini alma|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Mevcut C çalışma zamanı dosya tanımlayıcısı ile ilişkili dönüş işletim sistemi dosya tanıtıcısı|
|[_isatty](../c-runtime-library/reference/isatty.md)|Karakter cihazı denetleme|
|[_locking](../c-runtime-library/reference/locking.md)|Dosyanın kilidi alanları|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C çalışma zamanı dosya tanımlayıcısı var olan işletim sistemi dosya tanıtıcısı ile ilişkilendirme|
|[_setmode](../c-runtime-library/reference/setmode.md)|Dosya çeviri modunu ayarlama|

## <a name="file-handling-routines-path-or-filename"></a>Dosya işleme rutinleri (yolu veya dosya adı)

Bu yordamların bir yol veya dosya adı tarafından belirtilen dosyalar üzerinde çalışır.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_erişim, _waccess](../c-runtime-library/reference/access-waccess.md), [_access_s, _waccess_s](../c-runtime-library/reference/access-s-waccess-s.md)|Dosya izin ayarı işaretleyin|
|[_chmod, _wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Dosya izin ayarı Değiştir|
|[_fullpath, _wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Göreli bir yol mutlak yol adını genişletin.|
|[_makepath, _wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [_makepath_s, _wmakepath_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Yol bileşenleri tek, tam yola Birleştir|
|[_mktemp, _wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [_mktemp_s, _wmktemp_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Benzersiz bir dosya adı oluşturun|
|[remove, _wremove](../c-runtime-library/reference/remove-wremove.md)|Dosya Sil|
|[rename, _wrename](../c-runtime-library/reference/rename-wrename.md)|Dosyayı yeniden adlandır|
|[_splitpath, _wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [_splitpath_s, _wsplitpath_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Bileşenlerine yolu ayrıştırılamıyor|
|[_stat, _stat64, _stati64, _wstat, _wstat64, _wstati64](../c-runtime-library/reference/stat-functions.md)|Adlandırılmış dosya dosya durumu bilgilerini alma|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Program tarafından oluşturulan yeni dosyaları için varsayılan izin maskesini ayarlama|
|[_unlink, _wunlink](../c-runtime-library/reference/unlink-wunlink.md)|Dosya Sil|

## <a name="file-handling-routines-open-file"></a>Dosya işleme rutinleri (açık dosya)

Bu yordamların dosyalarını açın.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Bir dosyayı açar ve açık dosyaya bir işaretçi döndürür.|
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Dosya Paylaşımı ile bir akış açmayın ve açık dosyaya bir işaretçi döndürür.|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Bir dosyayı açar ve açık dosya için bir dosya tanımlayıcısını döndürür.|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Dosya Paylaşımı ile bir dosya açın ve açık dosyaya bir dosya tanımlayıcısını döndürür.|
|[_pipe](../c-runtime-library/reference/pipe.md)|Okuma ve yazma için bir kanal oluşturur.|
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Dosya işaretçisini yeniden atayın.|

Bu yordamların arasında dosya gösterimini değiştirmek için bir yol sağlayan bir `FILE` yapısı, bir dosya tanımlayıcısı ve Win32 dosya işleci.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Bir akış, düşük düzey g/ç için daha önce açıldı ve açık akışa bir işaretçi döndüren bir dosya ile ilişkilendirir.|
|[_fileno](../c-runtime-library/reference/fileno.md)|Bir akış ile ilişkili dosya tanımlayıcısını alır.|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Mevcut C çalışma zamanı dosya tanımlayıcısı ile ilişkili dönüş işletim sistemi dosya tanıtıcısı|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C çalışma zamanı dosya tanımlayıcısı, var olan bir işletim sistemi dosya tanıtıcısı ile ilişkilendirir.|

 Aşağıdaki Win32 işlevlerini de dosyalar ve kanallar açın:

- [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea)

- [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)

- [CreateNamedPipe](/windows/desktop/api/winbase/nf-winbase-createnamedpipea)

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Dizin Denetimi](../c-runtime-library/directory-control.md)<br/>
[Sistem Çağrıları](../c-runtime-library/system-calls.md)<br/>
