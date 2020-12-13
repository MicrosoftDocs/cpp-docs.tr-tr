---
description: 'Hakkında daha fazla bilgi edinin: _sopen_s _wsopen_s'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 14a15f78ad452873813f9a6eb4f65de93cd055b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137000"
---
# <a name="_sopen_s-_wsopen_s"></a>_sopen_s, _wsopen_s

Paylaşım için bir dosya açar. [_Sopen ve _wsopen](sopen-wsopen.md) bu SÜRÜMLERINDE, [CRT 'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

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

*PFH*<br/>
Dosya tanıtıcısı veya bir hata durumunda-1.

*filename*<br/>
Dosya adı.

*oflag*<br/>
İzin verilen işlem türü.

*shflag*<br/>
İzin verilen paylaşım türü.

*pmode*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan dönüş değeri bir hatayı gösterir; Bu durumda, **errno** aşağıdaki değerlerden birine ayarlanır.

|errno değeri|Koşul|
|-|-|
| **EACCES** |  Verilen yol bir dizin veya dosya salt okunurdur, ancak yazma işlemi için açık bir işlem denendi. |
| **EEXıST** |  **_O_CREAT** ve **_o_excl** bayrakları belirtildi, ancak *dosya adı* zaten var. |
| **EıNVAL** |  Geçersiz *oflag*, *shflag* veya *pmode* bağımsız değişkeni ya da *PFH* veya *filename* null bir işaretçiydi. |
| **EMFıLE** | Kullanılabilir başka dosya tanımlayıcısı yok. |
| **ENOENT** | Dosya veya yol bulunamadı. |

İşleve geçersiz bir bağımsız değişken geçirilmezse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve **EINVAL** döndürülür.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bir hata durumunda-1, *PFH* üzerinden döndürülür ( *PFH* null işaretçisiyse).

## <a name="remarks"></a>Açıklamalar

**_Sopen_s** işlevi dosya *adı* tarafından belirtilen dosyayı açar ve dosyayı *oflag* ve *shflag* tarafından tanımlanan şekilde paylaşılan okuma veya yazma için hazırlar. **_wsopen_s** , **_sopen_s** geniş karakterli bir sürümüdür; _wsopen_s *dosya adı* bağımsız  değişkeni, geniş karakterli bir dizedir. **_wsopen_s** ve **_sopen_s** aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen_s**|**_sopen_s**|**_sopen_s**|**_wsopen_s**|

*Gecikme* tamsayı ifadesi, içinde tanımlanan bir veya daha fazla bildirim sabiti birleştirilerek oluşturulur \<fcntl.h> . İki veya daha fazla *sabit bağımsız değişkeni* bir şekilde kullandığınızda, BIT düzeyinde OR işleci ( **&#124;** ) ile birleştirilir.

|*oflag* sabiti|Davranış|
|-|-|
| **_O_APPEND** | Her yazma işleminden önce dosya işaretçisini dosyanın sonuna kaydırır. |
| **_O_BINARY** | Dosyayı ikili (çevrilmemiş) modda açar. (İkili modun açıklaması için bkz. [fopen](fopen-wfopen.md) .) |
| **_O_CREAT** | Bir dosya oluşturur ve yazmak için açar. Dosya *adı* tarafından belirtilen dosya varsa herhangi bir etkiye sahip değildir. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | Geçici olarak bir dosya oluşturur ve mümkünse disk boşaltılamaz. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_TEMPORARY** | Geçici olarak bir dosya oluşturur; Dosya, son dosya tanımlayıcısı kapatıldığında silinir. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; `_O_EXCL` | Dosya *adı* tarafından belirtilen bir dosya varsa bir hata değeri döndürür. Yalnızca **_O_CREAT** ile kullanıldığında geçerlidir. |
| **_O_NOINHERIT** | Paylaşılan bir dosya tanımlayıcısının oluşturulmasını engeller. |
| **_O_RANDOM** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim |
| **_O_RDONLY** | Yalnızca okuma için bir dosya açar. **_O_RDWR** veya **_O_WRONLY** ile belirtilemez. |
| **_O_RDWR** | Hem okuma hem de yazma için bir dosya açar. **_O_RDONLY** veya **_O_WRONLY** ile belirtilemez. |
| **_O_SEQUENTIAL** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir. |
| **_O_TEXT** | Metin (çevrilmiş) modunda bir dosya açar. (Daha fazla bilgi için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](fopen-wfopen.md).) |
| **_O_TRUNC** | Bir dosya açar ve sıfır uzunluğa kırpar; dosya yazma iznine sahip olmalıdır. **_O_RDONLY** ile belirtilemez. **_O_CREAT** **_O_TRUNC** , mevcut bir dosyayı açar veya bir dosya oluşturur. **Note:** **_O_TRUNC** bayrağı belirtilen dosyanın içeriğini yok eder. |
| **_O_WRONLY** | Yalnızca yazma için bir dosya açar. **_O_RDONLY** veya **_O_RDWR** ile belirtilemez. |
| **_O_U16TEXT** | Unicode UTF-16 modunda bir dosya açar. |
| **_O_U8TEXT** | Unicode UTF-8 modunda bir dosya açar. |
| **_O_WTEXT** | Unicode modunda bir dosya açar. |

Dosya erişim modunu belirtmek için **_O_RDONLY**, **_O_RDWR** veya **_O_WRONLY** belirtmeniz gerekir. Erişim modu için varsayılan değer yoktur.

**_O_WTEXT**, **_O_U8TEXT** veya **_O_U16TEXT** kullanarak Unicode modunda bir dosya açıldığında giriş işlevleri, dosyadaki okunan verileri, tür olarak depolanan UTF-16 verilerine çevirir **`wchar_t`** . Unicode modunda açılan bir dosyaya yazan işlevler, tür olarak depolanan UTF-16 verileri içeren arabellekler bekler **`wchar_t`** . Dosya UTF-8 olarak kodlanmışsa, UTF-16 verileri yazıldığında UTF-8 ' e çevrilir ve dosyanın UTF-8 kodlu içeriği okunarak UTF-16 ' a çevrilir. Unicode modunda tek sayıda bayt okuma veya yazma girişimi bir parametre doğrulama hatasına neden olur. Programınızda depolanan verileri UTF-8 olarak okumak veya yazmak için Unicode modu yerine bir metin veya ikili dosya modu kullanın. Gerekli tüm kodlama çevirilerinden siz sorumlusunuz.

**_Sopen_s** **_O_WRONLY**  |  **_O_APPEND** (ekleme modu) ve **_O_WTEXT**, **_O_U16TEXT** veya **_O_U8TEXT** ile çağrılırsa, ilk olarak dosyayı okumak ve yazmak için açmaya çalışır, ürün reçetesini okuyabilir ve sonra yalnızca yazmak üzere yeniden açabilirsiniz. Dosyayı okuma ve yazma için açmak başarısız olursa, dosyayı yalnızca yazma için açar ve Unicode modu ayarı için varsayılan değeri kullanır.

*Shflag* bağımsız değişkeni, içinde tanımlanan aşağıdaki bildirim sabitlerinden birini içeren sabit bir ifadedir \<share.h> .

|*shflag* sabiti|Davranış|
|-|-|
| **_SH_DENYRW** | Bir dosyaya okuma ve yazma erişimini reddeder. |
| **_SH_DENYWR** | Bir dosyaya yazma erişimini reddeder. |
| **_SH_DENYRD** | Bir dosyaya okuma erişimini reddeder. |
| **_SH_DENYNO** | Okuma ve yazma erişimine izin verir. |

*Pmode* bağımsız değişkeni, **_sopen** aksine her zaman gereklidir. **_O_CREAT** belirttiğinizde, dosya yoksa *pmode* , yeni dosya ilk kez kapatıldığında ayarlanan dosyanın izin ayarlarını belirtir. Aksi halde *pmode* yok sayılır. *pmode* , **_S_IWRITE** bildirim sabitlerinden birini veya her ikisini içeren bir tamsayı ifadesidir ve içinde tanımlanan **_S_IREAD** \<sys\stat.h> . Her iki sabit de verildiğinde, bit düzeyinde OR işleci ile birleştirilir. *Pmode* 'un anlamı aşağıdaki gibidir.

|*pmode*|Anlamı|
|-|-|
| **_S_IREAD** | Yalnızca okuma izni verilir. |
| **_S_IWRITE** | Yazma izni veriliyor. (Aslında, okuma ve yazma izni verir.) |
| **_S_IREAD** &#124; **_S_IWRITE** | Okuma ve yazma izni verildi. |

Yazma izni verilmezse, dosya salt okunurdur. Windows işletim sisteminde tüm dosyalar okunabilir; salt yazılır izin vermek mümkün değildir. Bu nedenle, **_S_IWRITE** ve **_S_IREAD**  |  **_S_IWRITE** modları eşdeğerdir.

**_sopen_s** izinler ayarlanmadan önce, geçerli dosya izni maskesini *pmode* 'a uygular. (Bkz. [_umask](umask.md).)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_sopen_s**|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|
|**_wsopen_s**|\<io.h> veya \<wchar.h>|\<fcntl.h>, \<sys/types.h>, \<sys/stat.h>, \<share.h>|

**_sopen_s** ve **_wsopen_s** Microsoft uzantılarıdır. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Locking](locking.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
