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
ms.openlocfilehash: 0e11c11b468ff6e058ccf5c75b000396e0473bfa
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747650"
---
# <a name="errno-constants"></a>errno Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <errno.h>
```

## <a name="remarks"></a>Açıklamalar

**Errno** sabitleri atanan değerler [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) çeşitli hata koşulları durumunda.

ERRNO. H tanımlarını içeren **errno** değerleri. Ancak, ERRNO verilen tüm tanımları. H 32-bit Windows işletim sistemlerinde kullanılır. Bazı ERRNO değeri. H UNIX ailesi işletim sistemleri ile uyumluluğu korumak için mevcut.

**Errno** değerler 32-bit Windows işletim sisteminde bir alt kümesini değerlerini **errno** XENIX sistemlerde. Bu nedenle, **errno** değeri değildir Windows işletim sistemlerinden sistem çağrısı tarafından döndürülen gerçek hata kodu ile aynı. Gerçek işletim sistemi hata kodu erişmek için [_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu değeri içeren bir değişkeni.

Aşağıdaki **errno** değerler desteklenir:

|Sabit|Açıklama|
|-|-|
|**ECHILD**|Üretilmiş işlem yok.|
|**EAGAIN**|Daha fazla işlem yok. Daha fazla işlem yuva yok, veya bellek yeterli değil veya iç içe geçme düzeyi üst sınırına ulaşıldı yeni bir işlem oluşturma girişimi başarısız oldu.|
|**E2BIG**|Bağımsız değişken listesi çok uzun.|
|**SPAWN**|İzin reddedildi. Dosya izin ayarının belirtilen erişim izin vermez. Bu hata, bir dosyaya erişmek için girişiminde bulunuldu belirtir (veya bazı durumlarda, bir dizin), dosya özniteliklerini bir şekilde uyumsuz.<br/><br/>Örneğin, yazma için mevcut bir salt okunur dosyasını açın veya bir dizin dosyası açmak için açık değil, bir dosyadan okuma denemesi yapıldığında hata oluşabilir. MS-DOS işletim sistemi sürümlerinde 3.0 ve sonraki sürümler altında **SPAWN** bir kilitleme veya paylaşım ihlali da gösterebilir.<br/><br/>Hata, bir dosya veya dizin yeniden adlandırmak veya varolan bir dizin kaldırmak için bir girişimi de oluşabilir.|
|**EBADF**|Hatalı dosya numarası. İki olası nedeni vardır: (1) belirtilen dosya tanımlayıcısı, geçerli bir değer değil veya açık olan bir dosyaya başvurmuyor. (2) bir dosya veya cihaz için yalnızca okuma erişimi açılan yazmak için girişimde bulunuldu.|
|**EDEADLOCK**|Kaynak kilitlenmesi oluşabilir. Bir matematiksel işlev için bağımsız değişken işlev etki alanında değil.|
|**EDOM**|Matematik bağımsız değişkeni.|
|**EEXIST**|Dosya mevcut. Zaten bir dosya oluşturmak için girişiminde bulunuldu. Örneğin, **_O_CREAT** ve **_O_EXCL** bayrakları içinde belirtilen bir **_aç** çağrısı, ancak adlandırılmış dosyanın zaten mevcut.|
|**EILSEQ**|Geçersiz dizi bayta (örneğin, bir MBCS dizesindeki).|
|**EINVAL**|Geçersiz bağımsız değişken. Bir işlev için bağımsız değişkenlerden biri için geçersiz değer verildi. Örneğin, bir dosya işaretçisiyse konumlandırırken kaynak için verilen değer (bir çağrı yoluyla **fseek**) önce dosyanın bir başlangıç.|
|**EMFILE**|Çok fazla açık dosya. Daha fazla dosya açık şekilde hiçbir daha fazla dosya tanımlayıcısı kullanılabilir.|
|**ENOENT**|Böyle dosya veya dizin yok. Belirtilen dosya veya dizin yok veya bulunamadı. Bu ileti, belirtilen dosya yok veya varolan bir dizin yolu'nin bir bileşeni belirtmiyor olduğunda ortaya çıkabilir.|
|**ENOEXEC**|Exec biçim hatası. Yürütülebilir değil veya geçersiz bir yürütülebilir dosya biçimine sahip bir dosyayı yürütmek için girişimde bulunuldu.|
|**ENOMEM**|Yeterli çekirdek. Yeterli bellek yok denenen işleci için kullanılabilir. Örneğin, bu iletiyi bir alt işlemi yürütmek için bellek yetersiz olduğunda ya da ayırma isteği oluşabilir bir **_getcwd** çağrı kullanılamaz memnun.|
|**ENOSPC**|Aygıtta kalan alanı yok. Yazma için daha fazla yer yok (örneğin, disk dolu olduğunda) cihazın kullanılabilir.|
|**ERANGE**|Sonuç çok büyük. Bir matematiksel işlev için bağımsız değişken sonuç anlam kısmi ya da toplam kaybına kaynaklanan çok büyük. Bir bağımsız değişken beklenenden daha büyük olduğunda bu hatayı diğer işlevlerde da meydana gelebilir (örneğin, *arabellek* bağımsız değişkeni **_getcwd** beklenenden daha uzun).|
|**EXDEV**|Çapraz cihaz bağlantısı. Dosyayı farklı bir cihaz için taşımak için bir girişimde bulunuldu (kullanarak **Yeniden Adlandır** işlevi).|
|**STRUNCATE**|Bir dizeyi kopyalama ya da birleştirme kesilmiş bir dizede sonuçlandı. Bkz: [_TRUNCATE](../c-runtime-library/truncate.md).

Aşağıdaki değerleri, POSIX ile uyumluluk için desteklenir. Bunlar POSIX olmayan sistemlerde gerekli değerler.

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
