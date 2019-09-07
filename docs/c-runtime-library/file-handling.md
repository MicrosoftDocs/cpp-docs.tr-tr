---
title: Dosya İşleme
ms.date: 11/04/2016
f1_keywords:
- c.files
helpviewer_keywords:
- files [C++], handling
- files [C++], opening
- files [C++], manipulating
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
ms.openlocfilehash: 2a5c6ec3a70a85bf81f00b104d0c505677f609ac
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740062"
---
# <a name="file-handling"></a>Dosya İşleme

Dosyaları oluşturmak, silmek ve işlemek ve dosya erişim izinlerini ayarlamak ve denetlemek için bu yordamları kullanın.

C çalışma zamanı kitaplıklarının, herhangi bir anda açık olabilecek dosya sayısı için 512 sınırı vardır. En fazla dosya tanımlayıcısı sayısı veya dosya akışı açılmaya çalışıldığında program hatasına neden olur. Bu sayıyı değiştirmek için [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) kullanın.

## <a name="file-handling-routines-file-descriptor"></a>Dosya IŞLEME yordamları (dosya tanımlayıcısı)

Bu yordamlar bir dosya tanımlayıcısı tarafından belirlenen dosyalar üzerinde çalışır.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_chsize](../c-runtime-library/reference/chsize.md),[_chsize_s](../c-runtime-library/reference/chsize-s.md)|Dosya boyutunu değiştir|
|[_filelength, _filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Dosya uzunluğunu al|
|[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Tanımlayıcıda dosya durum bilgilerini al|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Var olan C çalışma zamanı dosya tanımlayıcısıyla ilişkili işletim sistemi dosya tanıtıcısını döndürür|
|[_isatty](../c-runtime-library/reference/isatty.md)|Karakter cihazını denetle|
|[_locking](../c-runtime-library/reference/locking.md)|Dosya alanını kilitle|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C çalışma zamanı dosya tanımlayıcısını var olan işletim sistemi dosyası tanıtıcısıyla ilişkilendir|
|[_setmode](../c-runtime-library/reference/setmode.md)|Dosya çevirisi modunu ayarla|

## <a name="file-handling-routines-path-or-filename"></a>Dosya IŞLEME yordamları (yol veya dosya adı)

Bu yordamlar bir yol veya dosya adı tarafından belirtilen dosyalar üzerinde çalışır.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_access, _waccess](../c-runtime-library/reference/access-waccess.md), [_access_s, _waccess_s](../c-runtime-library/reference/access-s-waccess-s.md)|Dosya izni ayarını denetle|
|[_chmod, _wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Dosya değiştirme izni ayarı|
|[_fullpath, _wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Göreli yolu mutlak yol adına Genişlet|
|[_makepath, _wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [_makepath_s, _wmakepath_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Yol bileşenlerini tek, tam yol halinde Birleştir|
|[_mktemp, _wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [_mktemp_s, _wmktemp_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Benzersiz dosya adı oluştur|
|[remove, _wremove](../c-runtime-library/reference/remove-wremove.md)|Dosyayı Sil|
|[rename, _wrename](../c-runtime-library/reference/rename-wrename.md)|Dosyayı yeniden adlandır|
|[_splitpath, _wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [_splitpath_s, _wsplitpath_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Yolu bileşenlere Ayrıştır|
|[_stat, _stat64, _stati64, _wstat, _wstat64, _wstati64](../c-runtime-library/reference/stat-functions.md)|Adlandırılmış dosya üzerinde dosya durum bilgilerini al|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Program tarafından oluşturulan yeni dosyalar için varsayılan izin maskesini ayarla|
|[_unlink, _wunlink](../c-runtime-library/reference/unlink-wunlink.md)|Dosyayı Sil|

## <a name="file-handling-routines-open-file"></a>Dosya IŞLEME yordamları (dosya aç)

Bu yordamlar dosyaları açar.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Bir dosya açar ve açık dosyaya bir işaretçi döndürür.|
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Dosya paylaşımı olan bir akış açın ve açık dosyaya bir işaretçi döndürür.|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Bir dosya açar ve açılan dosyanın dosya tanımlayıcısını döndürür.|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Dosya paylaşımı olan bir dosya açın ve açık dosyaya bir dosya tanımlayıcısı döndürür.|
|[_pipe](../c-runtime-library/reference/pipe.md)|Okuma ve yazma için bir kanal oluşturur.|
|[serbest açık, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Bir dosya işaretçisini yeniden atayın.|

Bu yordamlar, bir `FILE` yapı, dosya tanımlayıcısı ve bir Win32 dosya tutamacı arasında dosyanın gösterimini değiştirmek için bir yol sağlar.

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Daha önce alt düzey g/ç için açılan bir dosyayla bir akış ilişkilendirir ve açık akışa bir işaretçi döndürür.|
|[_fileno](../c-runtime-library/reference/fileno.md)|Bir akışla ilişkili dosya tanımlayıcısını alır.|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Var olan C çalışma zamanı dosya tanımlayıcısıyla ilişkili işletim sistemi dosya tanıtıcısını döndürür|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C çalışma zamanı dosya tanımlayıcısını var olan bir işletim sistemi dosya tanıtıcısı ile ilişkilendirir.|

Aşağıdaki Win32 işlevleri de dosyaları ve kanalları açar:

- [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew)

- [CreatePipe](/windows/win32/api/namedpipeapi/nf-namedpipeapi-createpipe)

- [CreateNamedPipe](/windows/win32/api/winbase/nf-winbase-createnamedpipea)

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Dizin Denetimi](../c-runtime-library/directory-control.md)<br/>
[Sistem Çağrıları](../c-runtime-library/system-calls.md)<br/>
