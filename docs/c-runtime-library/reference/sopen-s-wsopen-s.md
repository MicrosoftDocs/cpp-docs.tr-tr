---
title: _sopen_s, _wsopen_s
ms.date: 4/2/2020
api_name:
- _sopen_s
- _wsopen_s
- _o__sopen_s
- _o__wsopen_s
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _sopen_s
- wsopen_s
- _wsopen_s
- sopen_s
helpviewer_keywords:
- sopen_s function
- _wsopen_s function
- wsopen_s function
- opening files, for sharing
- files [C++], opening
- _sopen_s function
- files [C++], sharing
ms.assetid: 059a0084-d08c-4973-9174-55e391b72aa2
ms.openlocfilehash: 81feacae0e4608512e7325c57e7f2b96bcf2cdde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356496"
---
# <a name="_sopen_s-_wsopen_s"></a>_sopen_s, _wsopen_s

Paylaşım için bir dosya açar. [_sopen ve _wsopen](sopen-wsopen.md) bu [sürümlerinde, CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _sopen_s(
   int* pfh,
   const char *filename,
   int oflag,
   int shflag,
   int pmode
);
errno_t _wsopen_s(
   int* pfh,
   const wchar_t *filename,
   int oflag,
   int shflag,
   int pmode,
);
```

### <a name="parameters"></a>Parametreler

*Pfh*<br/>
Dosya işlemi veya hata durumunda -1.

*filename*<br/>
Dosya adı.

*oflag*<br/>
İzin verilen türde operasyonlar.

*shflag*<br/>
Paylaşmanın izin verilen türden bir şey.

*pmode*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan bir geri dönüş değeri bir hata gösterir; bu durumda **errno** aşağıdaki değerlerden birine ayarlanır.

|errno değeri|Koşul|
|-|-|
| **EACCES** |  Verilen yol bir dizin veya dosya salt okunur, ancak yazmaya açık bir işlem denendi. |
| **EEXIST** |  **_O_CREAT** ve **_O_EXCL** bayrakları belirtilmiş, ancak *dosya adı* zaten var. |
| **Eınval** |  Geçersiz *oflag*, *shflag*, veya *pmode* bağımsız değişken, ya da *pfh* veya *filename* null işaretçi oldu. |
| **EMFILE** | Kullanılabilir dosya tanımlayıcısı yok. |
| **Enoent** | Dosya veya yol bulunamadı. |

İşleve geçersiz bir bağımsız değişken aktarılırsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve **EINVAL** döndürülür.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [errno, _doserrno, _sys_errlist ve _sys_nerr'a](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

Bir hata durumunda, -1 *pfh* üzerinden döndürülür *(pfh* null işaretçi olmadığı sürece).

## <a name="remarks"></a>Açıklamalar

**_sopen_s** işlevi *dosya adı* ile belirtilen dosyayı açar ve *oflag* ve *sayılt*tarafından tanımlandığı gibi, paylaşılan okuma veya yazma için dosyayı hazırlar. **_wsopen_s** **_sopen_s**geniş karakterli bir versiyonudur; **_wsopen_s** için *dosya adı* bağımsız değişkeni geniş karakterli bir dizedir. **_wsopen_s** ve **_sopen_s** aynı şekilde aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen_s**|**_sopen_s**|**_sopen_s**|**_wsopen_s**|

*Tamsayı* ifadesi fcntl.h> tanımlanan \<bir veya daha fazla manifesto sabiti birleştirilerek oluşur. İki veya daha fazla sabit *oflag*bağımsız değişkenini oluşturduğunda, bitwise-OR işleci **(&#124;)** ile birleştirilir.

|*oflag sabiti*|Davranış|
|-|-|
| **_O_APPEND** | Her yazma işleminden önce dosya işaretçisini dosyanın sonuna taşır. |
| **_o_bınary** | Dosyayı ikili (çevrilmemiş) modda açar. (İkili modun açıklaması için [bkz.](fopen-wfopen.md) |
| **_O_CREAT** | Bir dosya oluşturur ve yazmak için açar. *Dosya adı* ile belirtilen dosya varsa hiçbir etkisi yoktur. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | Bir dosyayı geçici olarak oluşturur ve mümkünse diske floş yapmaz. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_TEMPORARY** | Geçici olarak bir dosya oluşturur; son dosya tanımlayıcısı kapatıldığında dosya silinir. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124;`_O_EXCL` | *Dosya adı* ile belirtilen bir dosya varsa hata değeri verir. Yalnızca **_O_CREAT**ile kullanıldığında geçerlidir. |
| **_O_NOINHERIT** | Paylaşılan bir dosya tanımlayıcısının oluşturulmasını engeller. |
| **_O_RANDOM** | Önbelleğe almanın diskten rasgele erişim için en iyi duruma getirilmiş, ancak bu amaçla kullanılmadığını belirtir. |
| **_O_RDONLY** | Yalnızca okumak için bir dosya açar. **_O_RDWR** veya **_O_WRONLY**ile belirtilemez. |
| **_O_RDWR** | Hem okuma hem de yazma için bir dosya açar. **_O_RDONLY** veya **_O_WRONLY**ile belirtilemez. |
| **_O_SEQUENTIAL** | Önbelleğe almanın diskten sıralı erişim için en iyi duruma getirilmiş, ancak bu amaçla değil, en iyi duruma getirilmiştir. |
| **_o_text** | Metin (çevrilmiş) modda bir dosyayı açar. (Daha fazla bilgi için [Metin ve İkili Mod Dosyası G/Ç'ye](../../c-runtime-library/text-and-binary-mode-file-i-o.md) bakın ve [açın.)](fopen-wfopen.md) |
| **_O_TRUNC** | Bir dosyayı açar ve sıfır uzunluğa indirir; dosya yazma iznine sahip olmalıdır. **_O_RDONLY**ile belirtilemez. **_O_TRUNC** **_O_CREAT** ile kullanılan varolan bir dosyayı açar veya bir dosya oluşturur. **Not:** **_O_TRUNC** bayrağı belirtilen dosyanın içeriğini yok eder. |
| **_O_WRONLY** | Yalnızca yazmak için bir dosya açar. **_O_RDONLY** veya **_O_RDWR**ile belirtilemez. |
| **_O_U16TEXT** | Unicode UTF-16 modunda bir dosya açar. |
| **_O_U8TEXT** | Unicode UTF-8 modunda bir dosya açar. |
| **_O_WTEXT** | Unicode modunda bir dosya yı açar. |

Dosya erişim modunu belirtmek için **_O_RDONLY,** **_O_RDWR**veya **_O_WRONLY**belirtmeniz gerekir. Erişim modu için varsayılan değer yoktur.

Bir dosya unicode modunda **_O_WTEXT**, **_O_U8TEXT**veya **_O_U16TEXT**kullanılarak açıldığında, giriş işlevleri dosyadan okunan verileri **wchar_t**türü olarak depolanan UTF-16 verilerine çevirir. Unicode modunda açılan bir dosyaya yazılan **işlevler,** wchar_t türü olarak depolanan UTF-16 verileri içeren arabellekleri bekler. Dosya UTF-8 olarak kodlanırsa, UTF-16 verileri yazıldığında UTF-8'e çevrilir ve dosyanın UTF-8 kodlanmış içeriği okunduğunda UTF-16'ya çevrilir. Unicode modunda tek sayıda bayt okuma veya yazma girişimi parametre doğrulama hatasına neden olur. Programınızda UTF-8 olarak depolanan verileri okumak veya yazmak için Unicode modu yerine metin veya ikili dosya modu kullanın. Gerekli kodlama çevirisiden siz sorumlusunuz.

**_sopen_s** **_O_WRONLY** | **_O_APPEND** (ek modu) ve **_O_WTEXT**, **_O_U16TEXT**, veya **_O_U8TEXT**ile çağrılırsa, ilk okuma ve yazma için dosyayı açmak için çalışır, BOM okumak, sonra sadece yazmak için yeniden. Okuma ve yazma için dosyayı açmak başarısız olursa, dosyayı yalnızca yazmak için açar ve Unicode modu ayarı için varsayılan değeri kullanır.

Bağımsız *değişken,* \<share.h> tanımlanan aşağıdaki bildirim sabitlerinden birinden oluşan sabit bir ifadedir.

|*shflag sabiti*|Davranış|
|-|-|
| **_SH_DENYRW** | Bir dosyayı okuma ve yazma yı reddeder. |
| **_SH_DENYWR** | Bir dosyaya erişimi yazmayı reddediyor. |
| **_SH_DENYRD** | Dosyaya erişimi okumayı reddediyor. |
| **_SH_DENYNO** | Okuma ve yazma erişimine izin verir. |

*Pmode* bağımsız değişkeni her zaman, **_sopen**aksine gereklidir. **_O_CREAT**belirtdiğinizde, dosya yoksa, *pmode* yeni dosya ilk kez kapatıldığında ayarlanan dosyanın izin ayarlarını belirtir. Aksi takdirde, *pmode* yoksayılır. *pmode,* **_S_IWRITE** ve **_S_IREAD**olan ve sys\stat.h> tanımlanan \<manifesto sabitlerinden birini veya her ikisini içeren bir tamsayı ifadesidir. Her iki sabit de verildiğinde, bitwise-OR işleci ile birleştirilir. *Pmode* anlamı aşağıdaki gibidir.

|*pmode*|Anlamı|
|-|-|
| **_S_IREAD** | Sadece okumaya izin verilir. |
| **_S_IWRITE** | Yazmaya izin verilir. (Aslında, okuma ve yazma izin verir.) |
| **_S_IREAD** &#124; **_S_IWRITE** | Okuma ve yazmaya izin verilir. |

Yazma izni verilmezse, dosya salt okunur. Windows işletim sisteminde, tüm dosyalar okunabilir; yalnızca yazma izni vermek mümkün değildir. Bu nedenle, **_S_IWRITE** ve **_S_IREAD** | **_S_IWRITE** modları eşdeğerdir.

**_sopen_s,** izinler ayarlıolmadan önce geçerli dosya izin maskesini *pmode'e* uygular. (Bkz. [_umask](umask.md).)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_sopen_s**|\<io.h>|\<fcntl.h>, \<sys\types.h \<>, sys\stat.h>, \<share.h>|
|**_wsopen_s**|\<io.h> \<veya wchar.h>|\<fcntl.h>, \<sys/types.h \<>, sys/stat.h>, \<share.h>|

**_sopen_s** ve **_wsopen_s** Microsoft uzantılarıdır. Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_locking](locking.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
