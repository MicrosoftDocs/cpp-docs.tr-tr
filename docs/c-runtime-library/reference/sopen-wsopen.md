---
title: _sopen, _wsopen
ms.date: 4/2/2020
api_name:
- _sopen
- _wsopen
- _o__sopen
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
ms.openlocfilehash: b02219ba0afa37fdff02b6848540064d12cd001d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229382"
---
# <a name="_sopen-_wsopen"></a>_sopen, _wsopen

Paylaşım için bir dosya açar. Bu işlevlerin daha güvenli sürümleri mevcuttur: bkz. [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md).

## <a name="syntax"></a>Söz dizimi

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

*filename*<br/>
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
| **EEXıST** | **_O_CREAT** ve **_o_excl** bayrakları belirtildi, ancak *dosya adı* zaten var. |
| **EıNVAL** | Geçersiz *oflag* veya *shflag* bağımsız değişkeni. |
| **EMFıLE** | Kullanılabilir başka dosya tanımlayıcısı yok. |
| **ENOENT** | Dosya veya yol bulunamadı. |

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Sopen** işlevi dosya *adı* tarafından belirtilen dosyayı açar ve dosyayı *oflag* ve *shflag*tarafından tanımlanan şekilde paylaşılan okuma veya yazma için hazırlar. **_wsopen** , **_sopen**geniş karakterli bir sürümüdür; _wsopen *dosya adı* bağımsız **_wsopen** değişkeni, geniş karakterli bir dizedir. **_wsopen** ve **_sopen** aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen**|**_sopen**|**_sopen**|**_wsopen**|

*Gecikme* tamsayı ifadesi, içinde tanımlanan aşağıdaki bildirim sabitlerinden biri veya daha fazlası birleştirilerek oluşturulur \<fcntl.h> . İki veya daha fazla *sabit bağımsız değişkeni*bir şekilde kullandığınızda, BIT düzeyinde OR işleci ( **&#124;** ) ile birleştirilir.

|*oflag* sabiti|Davranış|
|-|-|
| **_O_APPEND** | Her yazma işleminden önce dosya işaretçisini dosyanın sonuna kaydırır. |
| **_O_BINARY** | Dosyayı ikili (çevrilmemiş) modda açar. (İkili modun açıklaması için bkz. [fopen](fopen-wfopen.md) .) |
| **_O_CREAT** | Bir dosya oluşturur ve yazmak için açar. Dosya *adı* tarafından belirtilen dosya varsa herhangi bir etkiye sahip değildir. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | Geçici olarak bir dosya oluşturur ve mümkünse disk boşaltılamaz. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_TEMPORARY** | Geçici olarak bir dosya oluşturur; Dosya, son dosya tanımlayıcısı kapatıldığında silinir. **_O_CREAT** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124;`_O_EXCL` | Dosya *adı* tarafından belirtilen bir dosya varsa bir hata değeri döndürür. Yalnızca **_O_CREAT**ile kullanıldığında geçerlidir. |
| **_O_NOINHERIT** | Paylaşılan bir dosya tanımlayıcısının oluşturulmasını engeller. |
| **_O_RANDOM** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim |
| **_O_RDONLY** | Yalnızca okuma için bir dosya açar. **_O_RDWR** veya **_O_WRONLY**ile belirtilemez. |
| **_O_RDWR** | Hem okuma hem de yazma için bir dosya açar. **_O_RDONLY** veya **_O_WRONLY**ile belirtilemez. |
| **_O_SEQUENTIAL** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir. |
| **_O_TEXT** | Metin (çevrilmiş) modunda bir dosya açar. (Daha fazla bilgi için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](fopen-wfopen.md).) |
| **_O_TRUNC** | Bir dosya açar ve sıfır uzunluğa kırpar; dosya yazma iznine sahip olmalıdır. **_O_RDONLY**ile belirtilemez. **_O_CREAT** **_O_TRUNC** , mevcut bir dosyayı açar veya bir dosya oluşturur. **Note:** **_O_TRUNC** bayrağı belirtilen dosyanın içeriğini yok eder. |
| **_O_WRONLY** | Yalnızca yazma için bir dosya açar. **_O_RDONLY** veya **_O_RDWR**ile belirtilemez. |
| **_O_U16TEXT** | Unicode UTF-16 modunda bir dosya açar. |
| **_O_U8TEXT** | Unicode UTF-8 modunda bir dosya açar. |
| **_O_WTEXT** | Unicode modunda bir dosya açar. |

Dosya erişim modunu belirtmek için **_O_RDONLY**, **_O_RDWR**veya **_O_WRONLY**belirtmeniz gerekir. Erişim modu için varsayılan değer yoktur.

**_O_WTEXT**, **_O_U8TEXT**veya **_O_U16TEXT**kullanarak Unicode modunda bir dosya açıldığında giriş işlevleri, dosyadaki okunan verileri, tür olarak depolanan UTF-16 verilerine çevirir **`wchar_t`** . Unicode modunda açılan bir dosyaya yazan işlevler, tür olarak depolanan UTF-16 verileri içeren arabellekler bekler **`wchar_t`** . Dosya UTF-8 olarak kodlanmışsa, UTF-16 verileri yazıldığında UTF-8 ' e çevrilir ve dosyanın UTF-8 kodlu içeriği okunarak UTF-16 ' a çevrilir. Unicode modunda tek sayıda bayt okuma veya yazma girişimi bir parametre doğrulama hatasına neden olur. Programınızda depolanan verileri UTF-8 olarak okumak veya yazmak için Unicode modu yerine bir metin veya ikili dosya modu kullanın. Gerekli tüm kodlama çevirilerinden siz sorumlusunuz.

**_Sopen** **_O_WRONLY**  |  **_O_APPEND** (ekleme modu) ve **_O_WTEXT**, **_O_U16TEXT**veya **_O_U8TEXT**ile çağrılırsa, ilk olarak dosyayı okumak ve yazmak için açmaya çalışır, ürün reçetesini okuyabilir ve sonra yalnızca yazmak üzere yeniden açabilirsiniz. Dosyayı okuma ve yazma için açmak başarısız olursa, dosyayı yalnızca yazma için açar ve Unicode modu ayarı için varsayılan değeri kullanır.

*Shflag* bağımsız değişkeni, içinde tanımlanan aşağıdaki bildirim sabitlerinden birini içeren sabit bir ifadedir \<share.h> .

|*shflag* sabiti|Davranış|
|-|-|
| **_SH_DENYRW** | Bir dosyaya okuma ve yazma erişimini reddeder. |
| **_SH_DENYWR** | Bir dosyaya yazma erişimini reddeder. |
| **_SH_DENYRD** | Bir dosyaya okuma erişimini reddeder. |
| **_SH_DENYNO** | Okuma ve yazma erişimine izin verir. |

*Pmode* bağımsız değişkeni yalnızca **_O_CREAT** belirtildiğinde gereklidir. Dosya yoksa, *pmode* dosyanın yeni dosya ilk kez kapatıldığında ayarlanan izin ayarlarını belirtir. Aksi halde *pmode* yok sayılır. *pmode* , **_S_IWRITE** bildirim sabitlerinden birini veya her ikisini içeren bir tamsayı ifadesidir ve içinde tanımlanan **_S_IREAD** \<sys\stat.h> . Her iki sabit de verildiğinde, bit düzeyinde OR işleci ile birleştirilir. *Pmode* 'un anlamı aşağıdaki gibidir.

|*pmode*|Anlamı|
|-|-|
| **_S_IREAD** | Yalnızca okuma izni verilir. |
| **_S_IWRITE** | Yazma izni veriliyor. (Aslında, okuma ve yazma izni verir.) |
| **_S_IREAD** &#124; **_S_IWRITE** | Okuma ve yazma izni verildi. |

Yazma izni verilmezse, dosya salt okunurdur. Windows işletim sisteminde tüm dosyalar okunabilir; salt yazılır izin vermek mümkün değildir. Bu nedenle, **_S_IWRITE** ve **_S_IREAD**  |  **_S_IWRITE** modları eşdeğerdir.

**_sopen** izinler ayarlanmadan önce, geçerli dosya izni maskesini *pmode* 'a uygular. (Bkz. [_umask](umask.md).)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_sopen**|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|
|**_wsopen**|\<io.h> veya \<wchar.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Locking](locking.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
