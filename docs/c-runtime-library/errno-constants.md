---
title: errno sabitleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98cc4c3afa245c55344454d4c96ea22d70905e0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="errno-constants"></a>errno Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <errno.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Errno** değerler atanan sabitleri [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) çeşitli hata koşulları durumunda.  
  
 ERRNO. H tanımlarını içeren **errno** değerleri. Ancak, ERRNO verilen tüm tanımlar. H 32 bit Windows işletim sistemlerinde kullanılır. Bazı ERRNO değerleri. H UNIX ailesi işletim sistemleri ile uyumluluğu korumak için mevcut.  
  
 **Errno** 32-bit Windows işletim sistemi değerler için değerleri alt ağını **errno** XENIX sistemlerinde. Bu nedenle, **errno** değeri değildir Windows işletim sistemlerinden sistem çağrısı tarafından döndürülen gerçek hata kodu ile aynı. Gerçek işletim sistemi hata kodu erişmek için [_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu değeri içeren değişkenin.  
  
 Aşağıdaki **errno** değerler desteklenir:  
  
 **ECHILD**  
 Oluşturulan hiçbir işlem.  
  
 **EAGAIN**  
 Daha fazla hiçbir işlem. Yeni bir işlem oluşturma girişimi başarısız oldu, daha fazla işlem yuva yok veya yeterli bellek olmadığından veya iç içe geçme düzeyi üst sınırına ulaşıldı.  
  
 **E2BIG**  
 Bağımsız değişken listesi çok uzun.  
  
 **EACCES**  
 İzni reddedildi. Dosya izni ayarı belirtilen erişim izin vermiyor. Bir dosyaya erişmek için girişimde bulunuldu, bu hata olmadığını gösterir (veya bazı durumlarda, bir dizin) içinde bir şekilde uyumlu dosyanın öznitelikleri.  
  
 Örneğin, yazma için mevcut bir salt okunur dosyasını açın veya bir dosya yerine bir dizin açmak için açık değil, bir dosyadan okumak için bir girişimde hata oluşabilir. 3.0 ve sonraki, MS-DOS işletim sistemi sürümleri altında **EACCES** bir kilitleme veya paylaşım ihlali da gösterebilir.  
  
 Hata, bir dosya veya dizin yeniden adlandırmak veya varolan bir dizin kaldırmak için bir deneme da oluşabilir.  
  
 **EBADF**  
 Hatalı dosya sayısı. İki olası nedeni vardır: 1) belirtilen dosya tanımlayıcısı geçerli bir değer değil veya açık olan bir dosyaya başvurmuyor. 2) bir dosya veya salt okunur erişim için açıldı aygıt yazmak için bir bir girişimde bulunuldu.  
  
 **EDEADLOCK**  
 Kaynak kilitlenmesi oluşacak. Matematik işlevine bağımsız değişken işlevi etki alanında değil.  
  
 **EDOM**  
 Matematik bağımsız değişkeni.  
  
 **EEXIST**  
 Dosyaları mevcut. Zaten bir dosya oluşturmak için bir girişiminde bulunuldu. Örneğin, **_O_CREAT** ve **_O_EXCL** bayrakları belirtilir bir **_kurulum Aç** çağrısı, ancak adlandırılan dosyanın zaten mevcut.  
  
 **EILSEQ**  
 Geçersiz (örneğin, bir MBCS dizesinde) bayt dizisi.  
  
 **EINVAL**  
 Geçersiz bağımsız değişken. Bir işlev bağımsız değişkenlerinden biri için geçersiz değer verildi. Örneğin, bir dosya işaretçisini konumlandırma zaman başlangıç verilen değer (yapılan bir çağrı yoluyla **fseek**) dosyası başlangıç önce.  
  
 **EMFILE**  
 Çok fazla açık dosya. Daha fazla dosya açık şekilde hiçbir daha fazla dosya tanımlayıcıları kullanılabilir.  
  
 **ENOENT**  
 Böyle dosya veya dizin yok. Belirtilen dosya veya dizin yok veya bulunamıyor. Bu ileti belirtilen dosya yok veya bir bileşeni olan bir yol varolan bir dizin belirtmiyor olduğunda ortaya çıkabilir.  
  
 **ENOEXEC**  
 Exec biçim hatası. Yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz olan bir dosya yürütmek için girişimde bulunuldu.  
  
 **ENOMEM**  
 Yeterli çekirdek. Denenen işleci için yeterli bellek yok. Örneğin, bu iletiyi bir alt işlemi yürütmek yeterli kullanılabilir bellek yok veya ayırma isteği oluşabilir bir **_getcwd** çağrısı olamaz memnun.  
  
 **ENOSPC**  
 Aygıtta kalan alanı yok. Yazma için daha fazla yer yok (örneğin, disk dolu olduğunda) cihazın kullanılabilir.  
  
 **ERANGE**  
 Sonucu çok büyük. Matematik işlevi bağımsız değişken sonuç anlamlı kısmi veya toplam kaybına kaynaklanan çok büyük. Bir bağımsız değişken beklenenden daha büyük olduğunda bu hata ayrıca diğer işlevleri oluşabilir (örneğin, *arabellek* bağımsız değişkeni **_getcwd** beklenenden daha uzun).  
  
 **EXDEV**  
 Çapraz-aygıt bağlantısı. Bir dosyayı farklı bir cihaz taşımak için bir girişimde bulunuldu (kullanarak **yeniden adlandırma** işlevi).  
  
 **STRUNCATE**  
 Bir dize kopyalama ya da birleştirme kesilmiş dizesinde sonuçlandı. Bkz: [_TRUNCATE](../c-runtime-library/truncate.md).  
  
 Aşağıdaki değerleri POSIX ile uyumluluk için desteklenir. Bunlar POSIX olmayan sistemlerde gerekli değerlerdir.  
  
```  
#define E2BIG [argument list too long]  
#define EACCES [permission denied]  
#define EADDRINUSE [address in use]  
#define EADDRNOTAVAIL [address not available]  
#define EAFNOSUPPORT [address family not supported]  
#define EAGAIN [resource unavailable try again]  
#define EALREADY [connection already in progress]  
#define EBADF [bad file descriptor]  
#define EBADMSG [bad message]  
#define EBUSY [device or resource busy]  
#define ECANCELED [operation canceled]  
#define ECHILD [no child process]  
#define ECONNABORTED [connection aborted]  
#define ECONNREFUSED [connection refused]  
#define ECONNRESET [connection reset]  
#define EDEADLK [resource deadlock would occur]  
#define EDESTADDRREQ [destination address required]  
#define EDOM [argument out of domain]  
#define EEXIST [file exists]  
#define EFAULT [bad address]  
#define EFBIG [file too large]  
#define EHOSTUNREACH [host unreachable]  
#define EIDRM [identifier removed]  
#define EILSEQ [illegal byte sequence]  
#define EINPROGRESS [operation in progress]  
#define EINTR [interrupted]  
#define EINVAL [invalid argument]  
#define EIO [io error]  
#define EISCONN [already connected]  
#define EISDIR [is a directory]  
#define ELOOP [too many synbolic link levels]  
#define EMFILE [too many files open]  
#define EMLINK [too many links]  
#define EMSGSIZE [message size]  
#define ENAMETOOLONG [filename too long]  
#define ENETDOWN [network down]  
#define ENETRESET [network reset]  
#define ENETUNREACH [network unreachable]  
#define ENFILE [too many files open in system]  
#define ENOBUFS [no buffer space]  
#define ENODATA [no message available]  
#define ENODEV [no such device]  
#define ENOENT [no such file or directory]  
#define ENOEXEC [executable format error]  
#define ENOLCK [no lock available]  
#define ENOLINK [no link]  
#define ENOMEM [not enough memory]  
#define ENOMSG [no message]  
#define ENOPROTOOPT [no protocol option]  
#define ENOSPC [no space on device]  
#define ENOSR [no stream resources]  
#define ENOSTR [not a stream]  
#define ENOSYS [function not supported]  
#define ENOTCONN [not connected]  
#define ENOTDIR [not a directory]  
#define ENOTEMPTY [directory not empty]  
#define ENOTRECOVERABLE [state not recoverable]  
#define ENOTSOCK [not a socket]  
#define ENOTSUP [not supported]  
#define ENOTTY [inappropriate io control operation]  
#define ENXIO [no such device or address]  
#define EOPNOTSUPP [operation not supported]  
#define EOTHER [other]  
#define EOVERFLOW [value too large]  
#define EOWNERDEAD [owner dead]  
#define EPERM [operation not permitted]  
#define EPIPE [broken pipe]  
#define EPROTO [protocol error]  
#define EPROTONOSUPPORT [protocol not supported]  
#define EPROTOTYPE [wrong protocol type]  
#define ERANGE [result out of range]  
#define EROFS [read only file system]  
#define ESPIPE [invalid seek]  
#define ESRCH [no such process]  
#define ETIME [stream timeout]  
#define ETIMEDOUT [timed out]  
#define ETXTBSY [text file busy]  
#define EWOULDBLOCK [operation would block]  
#define EXDEV [cross device link]  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Sabitler](../c-runtime-library/global-constants.md)