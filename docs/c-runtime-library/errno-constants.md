---
title: errno Sabitleri
ms.date: 09/17/2018
f1_keywords:
- ENOEXEC
- ENOMEM
- E2BIG
- STRUNCATE
- ENOENT
- EMFILE
- EBADF
- EDEADLOCK
- EXDEV
- EILSEQ
- EINVAL
- EDOM
- EACCES
- ERANGE
- ENOSPC
- EAGAIN
- EEXIST
- ECHILD
helpviewer_keywords:
- ENOEXEC constant
- EBADF constant
- EAGAIN constant
- EINVAL constant
- ENOENT constant
- errno constants
- E2BIG constant
- EMFILE constant
- EDEADLOCK constant
- ENOSPC constant
- EDOM constant
- ENOMEM constant
- EACCES constant
- EEXIST constant
- STRUNCATE constant
- ERANGE constant
- ECHILD constant
- EXDEV constant
- EILSEQ constant
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
ms.openlocfilehash: 34f92bedfa9606c90196f2e3a5e47dc341b23aea
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898752"
---
# <a name="errno-constants"></a>errno Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <errno.h>
```

## <a name="remarks"></a>Açıklamalar

**Errno** değeri, çeşitli hata koşulları durumunda [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 'a atanan sabitlerdir.

ERRNO. H, **errno** değeri tanımlarını içerir. Ancak, ERRNO 'da verilen tüm tanımlar değildir. H, 32 bitlik Windows işletim sistemlerinde kullanılır. ERRNO içindeki bazı değerler. H, UNIX işletim sistemi ailesiyle uyumluluğu sürdürmek için mevcuttur.

32 bitlik bir Windows işletim sisteminde **errno** DEĞERI, XENIX sistemlerinde **errno** değerlerinin bir alt kümesidir. Bu nedenle, **errno** değeri, Windows işletim sistemlerinden bir sistem çağrısıyla döndürülen gerçek hata kodu ile aynı değildir. Gerçek işletim sistemi hata koduna erişmek için, bu değeri içeren [_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) değişkenini kullanın.

Aşağıdaki **errno** değeri desteklenir:

|Sabit|Açıklama|
|-|-|
|**ECHıLD**|Üretilen işlem yok.|
|**EAGAıN**|Başka işlem yok. Daha fazla işlem yuvası olmadığından veya yeterli bellek olmadığından veya en fazla iç içe geçme düzeyine ulaşıldığından, yeni bir işlem oluşturma girişimi başarısız oldu.|
|**E2BIG**|Bağımsız değişken listesi çok uzun.|
|**EACCES**|İzin reddedildi. Dosyanın izin ayarı belirtilen erişime izin vermiyor. Bu hata, bir dosyaya (veya bazı durumlarda bir dizin) dosyanın öznitelikleriyle uyumsuz bir şekilde erişmek için girişimde bulunuldu.<br/><br/>Örneğin, hata, açık olmayan bir dosyadan okuma, yazma için varolan salt bir dosyayı açma veya dosya yerine bir dizin açma için bir girişim yapıldığında meydana gelebilir. MS-DOS işletim sistemi sürümleri 3,0 ve üzeri sürümlerde, **EACCES** de bir kilitleme veya paylaşım ihlali gösterebilir.<br/><br/>Hata, bir dosyayı veya dizini yeniden adlandırma veya var olan bir dizini kaldırma girişimi içinde de oluşabilir.|
|**EBADF**|Hatalı dosya numarası. Olası iki neden vardır: 1) belirtilen dosya tanımlayıcısı geçerli bir değer değil veya açık bir dosyaya başvurmuyor. 2) salt okuma erişimi için açılan bir dosyaya veya cihaza yazma girişiminde bulunuldu.|
|**EDEADLOCK**|Kaynak kilitlenmesi meydana gelir. Math işlevinin bağımsız değişkeni işlevin etki alanında değil.|
|**EDOM**|Matematik bağımsız değişkeni.|
|**EEXıST**|Dosyalar var. Zaten var olan bir dosya oluşturulmaya çalışıldı. Örneğin, **_O_CREAT** ve **_O_EXCL** bayrakları bir **_open** çağrısında belirtilir, ancak adlandırılmış dosya zaten var.|
|**EıLSEQ**|Geçersiz bayt dizisi (örneğin, bir MBCS dizesinde).|
|**EıNVAL**|Geçersiz bağımsız değişken. Bir işleve bağımsız değişkenlerden biri için geçersiz bir değer verildi. Örneğin, bir dosya işaretçisi ( **fseek**çağrısı aracılığıyla) konumlandırılırken kaynak için verilen değer dosyanın başlangıcından öncedir.|
|**EMFıLE**|Çok fazla açık dosya. Daha fazla dosya tanımlayıcısı yok, bu nedenle başka dosya açılamaz.|
|**ENOENT**|Böyle bir dosya veya dizin yok. Belirtilen dosya veya dizin yok veya bulunamıyor. Bu ileti, belirtilen bir dosya yoksa veya bir yolun bileşeni var olan bir dizin belirtmezse gerçekleşebilir.|
|**ENOEXEC**|Exec biçim hatası. Yürütülebilir dosya olmayan veya geçersiz bir yürütülebilir dosya biçimine sahip bir dosya yürütülmeye çalışıldı.|
|**ENOMEM**|Yeterli çekirdek yok. Denenen operatör için yeterli bellek yok. Örneğin, bir alt işlemi yürütmek için yeterli bellek yoksa veya bir **_getcwd** çağrısındaki ayırma isteği karşılanmıyorsa bu ileti oluşabilir.|
|**ENOSPC**|Cihazda boşluk kalmadı. Cihazda yazma için daha fazla alan yok (örneğin, disk dolduğunda).|
|**ERANGE**|Sonuç çok büyük. Matematik işlevine yönelik bir bağımsız değişken çok büyük, sonuçta sonuçtaki kısmi veya toplam anlam kaybı ile sonuçlanır. Bu hata, bir bağımsız değişken beklenenden daha büyük olduğunda (örneğin, **_getcwd** için *arabellek* bağımsız değişkeni beklenenden uzun olduğunda) diğer işlevlerde da oluşabilir.|
|**EXDEV**|Cihazlar arası bağlantı. Bir dosyayı farklı bir cihaza taşıma denemesi yapıldı ( **yeniden adlandırma** işlevi kullanılarak).|
|**STRUNTE**|Dize kopyası veya birleştirme, kesilmiş bir dize ile sonuçlandı. Bkz. [_TRUNCATE](../c-runtime-library/truncate.md).

POSIX ile uyumluluk için aşağıdaki değerler desteklenir. Bunlar, POSIX olmayan sistemlerde gerekli değerlerdir.

```C
#define E2BIG /* argument list too long */
#define EACCES /* permission denied */
#define EADDRINUSE /* address in use */
#define EADDRNOTAVAIL /* address not available */
#define EAFNOSUPPORT /* address family not supported */
#define EAGAIN /* resource unavailable try again */
#define EALREADY /* connection already in progress */
#define EBADF /* bad file descriptor */
#define EBADMSG /* bad message */
#define EBUSY /* device or resource busy */
#define ECANCELED /* operation canceled */
#define ECHILD /* no child process */
#define ECONNABORTED /* connection aborted */
#define ECONNREFUSED /* connection refused */
#define ECONNRESET /* connection reset */
#define EDEADLK /* resource deadlock would occur */
#define EDESTADDRREQ /* destination address required */
#define EDOM /* argument out of domain */
#define EEXIST /* file exists */
#define EFAULT /* bad address */
#define EFBIG /* file too large */
#define EHOSTUNREACH /* host unreachable */
#define EIDRM /* identifier removed */
#define EILSEQ /* illegal byte sequence */
#define EINPROGRESS /* operation in progress */
#define EINTR /* interrupted */
#define EINVAL /* invalid argument */
#define EIO /* io error */
#define EISCONN /* already connected */
#define EISDIR /* is a directory */
#define ELOOP /* too many synbolic link levels */
#define EMFILE /* too many files open */
#define EMLINK /* too many links */
#define EMSGSIZE /* message size */
#define ENAMETOOLONG /* filename too long */
#define ENETDOWN /* network down */
#define ENETRESET /* network reset */
#define ENETUNREACH /* network unreachable */
#define ENFILE /* too many files open in system */
#define ENOBUFS /* no buffer space */
#define ENODATA /* no message available */
#define ENODEV /* no such device */
#define ENOENT /* no such file or directory */
#define ENOEXEC /* executable format error */
#define ENOLCK /* no lock available */
#define ENOLINK /* no link */
#define ENOMEM /* not enough memory */
#define ENOMSG /* no message */
#define ENOPROTOOPT /* no protocol option */
#define ENOSPC /* no space on device */
#define ENOSR /* no stream resources */
#define ENOSTR /* not a stream */
#define ENOSYS /* function not supported */
#define ENOTCONN /* not connected */
#define ENOTDIR /* not a directory */
#define ENOTEMPTY /* directory not empty */
#define ENOTRECOVERABLE /* state not recoverable */
#define ENOTSOCK /* not a socket */
#define ENOTSUP /* not supported */
#define ENOTTY /* inappropriate io control operation */
#define ENXIO /* no such device or address */
#define EOPNOTSUPP /* operation not supported */
#define EOTHER /* other */
#define EOVERFLOW /* value too large */
#define EOWNERDEAD /* owner dead */
#define EPERM /* operation not permitted */
#define EPIPE /* broken pipe */
#define EPROTO /* protocol error */
#define EPROTONOSUPPORT /* protocol not supported */
#define EPROTOTYPE /* wrong protocol type */
#define ERANGE /* result out of range */
#define EROFS /* read only file system */
#define ESPIPE /* invalid seek */
#define ESRCH /* no such process */
#define ETIME /* stream timeout */
#define ETIMEDOUT /* timed out */
#define ETXTBSY /* text file busy */
#define EWOULDBLOCK /* operation would block */
#define EXDEV /* cross device link */
```

## <a name="see-also"></a>Ayrıca bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)
