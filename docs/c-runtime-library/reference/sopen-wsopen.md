---
title: _sopen, _wsopen
ms.date: 11/04/2016
api_name:
- _sopen
- _wsopen
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsopen
- wsopen
- _sopen
- _tsopen
helpviewer_keywords:
- sopen function
- sharing files
- opening files, for sharing
- _sopen function
- wsopen function
- files [C++], opening
- files [C++], sharing
- _wsopen function
ms.assetid: a9d4cccf-06e9-414d-96fa-453fca88cc1f
ms.openlocfilehash: d337b2353ad15eade15235b4b5217a3b881bab1d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948055"
---
# <a name="_sopen-_wsopen"></a>_sopen, _wsopen

Paylaşım için bir dosya açar. Bu işlevlerin daha güvenli sürümleri mevcuttur: bkz. [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int _sopen(
   const char *filename,
   int oflag,
   int shflag [,
   int pmode ]
);
int _wsopen(
   const wchar_t *filename,
   int oflag,
   int shflag [,
   int pmode ]
);
```

### <a name="parameters"></a>Parametreler

*kısaltın*<br/>
Dosya adı.

*oflag*<br/>
İzin verilen işlem türü.

*shflag*<br/>
İzin verilen paylaşım türü.

*pmode*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, açılan dosyanın dosya tanımlayıcısını döndürür.

*Filename* veya *oflag* **null** bir işaretçisiyse veya *oflag* veya *shflag* geçerli bir değer aralığı içinde değilse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** değerini aşağıdaki değerlerden birine ayarlar.

|errno değeri|Koşul|
|-|-|
| **EACCES** | Verilen yol bir dizin veya dosya salt okunurdur, ancak yazma işlemi için açık bir işlem denendi. |
| **EEXIST** | **_O_creat** ve **_O_hariç** bayraklar belirtildi, ancak *dosya adı* zaten var. |
| **EINVAL** | Geçersiz *oflag* veya *shflag* bağımsız değişkeni. |
| **EMFILE** | Kullanılabilir başka dosya tanımlayıcısı yok. |
| **ENOENT** | Dosya veya yol bulunamadı. |

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Sopen** işlevi dosya *adı* tarafından belirtilen dosyayı açar ve dosyayı *oflag* ve *shflag*tarafından tanımlanan şekilde paylaşılan okuma veya yazma için hazırlar. **_wsopen** , **_sopen**öğesinin geniş karakterli bir sürümüdür; **_wsopen** için *filename* bağımsız değişkeni geniş karakterli bir dizedir. **_wsopen** ve **_sopen** , aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen**|**_sopen**|**_sopen**|**_wsopen**|

' In tamsayı *ifadesi,* \<fcntl. h > tanımlı aşağıdaki bildirim sabitlerinden bir veya daha fazlasını birleştirerek oluşturulur. İki veya daha fazla *sabit bağımsız değişkeni*bir şekilde kullandığınızda, BIT düzeyinde OR işleci ( **&#124;** ) ile birleştirilir.

|*oflag* sabiti|Davranış|
|-|-|
| **_O_APPEND** | Her yazma işleminden önce dosya işaretçisini dosyanın sonuna kaydırır. |
| **_O_BINARY** | Dosyayı ikili (çevrilmemiş) modda açar. (İkili modun açıklaması için bkz. [fopen](fopen-wfopen.md) .) |
| **_O_CREAT** | Bir dosya oluşturur ve yazmak için açar. Dosya *adı* tarafından belirtilen dosya varsa herhangi bir etkiye sahip değildir. **_O_creat** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | Geçici olarak bir dosya oluşturur ve mümkünse disk boşaltılamaz. **_O_creat** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_GEÇİCİDİR** | Geçici olarak bir dosya oluşturur; Dosya, son dosya tanımlayıcısı kapatıldığında silinir. **_O_creat** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124;` _O_EXCL` | Dosya *adı* tarafından belirtilen bir dosya varsa bir hata değeri döndürür. Yalnızca **_O_creat**ile kullanıldığında geçerlidir. |
| **_O_NOINHERIT** | Paylaşılan bir dosya tanımlayıcısının oluşturulmasını engeller. |
| **_O_RANDOM** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim |
| **_O_RDONLY** | Yalnızca okuma için bir dosya açar. **_O_rdwr** veya **_O_wronly**ile birlikte belirtilemez. |
| **_O_RDWR** | Hem okuma hem de yazma için bir dosya açar. **_O_rdonly** veya **_O_wronly**ile birlikte belirtilemez. |
| **_O_SEQUENTIAL** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir. |
| **_O_TEXT** | Metin (çevrilmiş) modunda bir dosya açar. (Daha fazla bilgi için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](fopen-wfopen.md).) |
| **_O_TRUNC** | Bir dosya açar ve sıfır uzunluğa kırpar; dosya yazma iznine sahip olmalıdır. **_O_rdonly**ile belirtilemez. **_O_creat** Ile kullanılan **_O_trunc** , var olan bir dosyayı açar veya bir dosya oluşturur. **Not:** **_O_trunc** bayrağı belirtilen dosyanın içeriğini yok eder. |
| **_O_WRONLY** | Yalnızca yazma için bir dosya açar. **_O_rdonly** veya **_O_rdwr**ile birlikte belirtilemez. |
| **_O_U16TEXT** | Unicode UTF-16 modunda bir dosya açar. |
| **_O_U8TEXT** | Unicode UTF-8 modunda bir dosya açar. |
| **_O_WTEXT** | Unicode modunda bir dosya açar. |

Dosya erişim modunu belirtmek için, **_O_rdonly**, **_O_RDWR**veya **_O_WRONLY**seçeneklerinden birini belirtmeniz gerekir. Erişim modu için varsayılan değer yoktur.

Bir dosya, **_O_wtext**, **_O_U8TEXT**veya **_O_u16text**kullanılarak Unicode modda açıldığında, giriş işlevleri dosyadan okunan verileri **wchar_t**türünde depolanan UTF-16 verilerine çevirir. Unicode modunda açılan bir dosyaya yazan işlevler **wchar_t**türü olarak depolanan UTF-16 verileri içeren arabellekler bekler. Dosya UTF-8 olarak kodlanmışsa, UTF-16 verileri yazıldığında UTF-8 ' e çevrilir ve dosyanın UTF-8 kodlu içeriği okunarak UTF-16 ' a çevrilir. Unicode modunda tek sayıda bayt okuma veya yazma girişimi bir parametre doğrulama hatasına neden olur. Programınızda depolanan verileri UTF-8 olarak okumak veya yazmak için Unicode modu yerine bir metin veya ikili dosya modu kullanın. Gerekli tüm kodlama çevirilerinden siz sorumlusunuz.

**_O_WRONLY** |  **_O_APPEND** (Append modu) ve **_O_WTEXT**, **_O_U16TEXT**veya **_O_U8TEXT**ile **_sopen** birlikte çağrılırsa, önce dosyayı okumak ve yazmak için açmayı dener, sonra da yeniden açın yalnızca yazma. Dosyayı okuma ve yazma için açmak başarısız olursa, dosyayı yalnızca yazma için açar ve Unicode modu ayarı için varsayılan değeri kullanır.

*Shflag* bağımsız değişkeni, \<Share. h > tanımlı aşağıdaki bildirim sabitlerinden birini içeren sabit bir ifadedir.

|*shflag* sabiti|Davranış|
|-|-|
| **_SH_DENYRW** | Bir dosyaya okuma ve yazma erişimini reddeder. |
| **_SH_DENYWR** | Bir dosyaya yazma erişimini reddeder. |
| **_SH_DENYRD** | Bir dosyaya okuma erişimini reddeder. |
| **_SH_DENYNO** | Okuma ve yazma erişimine izin verir. |

*Pmode* bağımsız değişkeni yalnızca **_O_creat** belirtildiğinde gereklidir. Dosya yoksa, *pmode* dosyanın yeni dosya ilk kez kapatıldığında ayarlanan izin ayarlarını belirtir. Aksi halde *pmode* yok sayılır. *pmode* , \< **smiwrite** ve **_s_iread**bildirim sabitlerinden birini ya da her ikisini içeren bir tamsayı ifadesidir ve SYS\Stat.h >. Her iki sabit de verildiğinde, bit düzeyinde OR işleci ile birleştirilir. *Pmode* 'un anlamı aşağıdaki gibidir.

|*pmode*|Açıklama|
|-|-|
| **_S_IREAD** | Yalnızca okuma izni verilir. |
| **_S_IWRITE** | Yazma izni veriliyor. (Aslında, okuma ve yazma izni verir.) |
| **_S_İREAD** &#124; **_S_İWRİTE** | Okuma ve yazma izni verildi. |

Yazma izni verilmezse, dosya salt okunurdur. Windows işletim sisteminde tüm dosyalar okunabilir; salt yazılır izin vermek mümkün değildir. Bu nedenle, **_s_iwrite** ve **_s_iread** |  **_s_iwrite** modları eşdeğerdir.

**_sopen** , geçerli dosya izni maskesini, izinler ayarlanmadan önce *pmode* 'a uygular. (Bkz. [_umask](umask.md).)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_sopen**|\<GÇ. h >|\<fcntl. h >, \<sys\types.h >, \<SYS\Stat.h >, \<Share. h >|
|**_wsopen**|\<GÇ. h > veya \<wchar. h >|\<fcntl. h >, \<sys\types.h >, \<SYS\Stat.h >, \<Share. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Kilitleme](locking.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
