---
title: _sopen, _wsopen
ms.date: 11/04/2016
apiname:
- _sopen
- _wsopen
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 4bb728b8e48190eb01e47dc9cd7de65a350f612d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626144"
---
# <a name="sopen-wsopen"></a>_sopen, _wsopen

Bir dosya paylaşımı için açar. Bu işlevlerin daha güvenli sürümleri mevcuttur: bkz [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md).

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

*Dosya adı*<br/>
Dosya adı.

*oflag*<br/>
İzin verilen işlemleri türü.

*shflag*<br/>
İzin verilen paylaşım türü.

*pmode*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, açık dosya için bir dosya tanımlayıcısını döndürür.

Varsa *filename* veya *oflag* olduğu bir **NULL** işaretçisi veya *oflag* veya *shflag* içinde geçerli değil aralık değerleri, geçersiz parametre açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** aşağıdaki değerlerden biri olarak.

|errno değeri|Koşul|
|-|-|
**SPAWN**|Verilen yol bir dizin veya dosya salt okunur olsa da yazma için açık bir işlem denendi.
**EEXIST**|**_O_CREAT** ve **_O_EXCL** bayrakları belirtildi, ancak *filename* zaten mevcut.
**EINVAL**|Geçersiz *oflag* veya *shflag* bağımsız değişken.
**EMFILE**|Daha fazla hiçbir dosya tanımlayıcısı kullanılabilir.
**ENOENT**|Dosya veya yol bulunamadı.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Sopen** işlevi tarafından belirtilen dosyayı açar *filename* dosyası tarafından tanımlanan paylaşılan okuma veya yazma için hazırlar *oflag* ve *shflag* . **_wsopen** geniş karakterli sürümüdür **_sopen**; *filename* bağımsız değişkeni **_wsopen** geniş karakterli bir dizedir. **_wsopen** ve **_sopen** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen**|**_sopen**|**_sopen**|**_wsopen**|

Tamsayı ifadesini *oflag* bir veya daha fazla Şunda tanımlı olan aşağıdaki bildirim sabitleri birleştirerek biçimlendirilmiş \<fcntl.h >. İki veya daha fazla sabit bağımsız değişkeni form zaman *oflag*, bit düzeyinde OR işleciyle birleşiminden oluşur ( **&#124;** ).

|*oflag* sabit|Davranış|
|-|-|
**_O_APPEND**|Dosya işaretçisini dosyanın her yazma işleminden önce sonuna taşır.
**_O_BINARY**|Dosya ikili (çevrilmemiş) modda açılır. (Bkz [fopen](fopen-wfopen.md) ikili modu açıklaması.)
**_O_CREAT**|Bir dosya oluşturur ve yazma için açar. Dosya belirtilen hiçbir etkisi *filename* bulunmaktadır. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT** &AMP;#124; **_O_SHORT_LIVED**|Geçici olarak bir dosya oluşturur ve mümkünse diske temizleme değil. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT** &AMP;#124; **_O_TEMPORARY**|Geçici olarak bir dosya oluşturur. son dosya tanımlayıcısı kapatıldığında dosya silinir. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT**&AMP;#124; ` _O_EXCL`|Bir hata değeri tarafından belirtilen dosya döndürür *filename* bulunmaktadır. Yalnızca ile kullanıldığında geçerlidir **_O_CREAT**.
**_O_NOINHERIT**|Paylaşılan dosya tanımlayıcısı oluşturulmasını engeller.
**_O_RANDOM**|Önbelleğe alma iyileştirildiğini, ancak rastgele erişim için diskten sınırlı olduğunu belirtir.
**_O_RDONLY**|Yalnızca okumak için bir dosya açar. İle belirtilemez **_O_RDWR** veya **_O_WRONLY**.
**_O_RDWR**|Hem okuma ve yazma için bir dosya açar. İle belirtilemez **_O_RDONLY** veya **_O_WRONLY**.
**_O_SEQUENTIAL**|Önbelleğe alma iyileştirildiğini, ancak sıralı erişim için diskten sınırlı olduğunu belirtir.
**_O_TEXT**|Metin (çevrilmiş) modunda bir dosya açar. (Daha fazla bilgi için [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](fopen-wfopen.md).)
**_O_TRUNC**|Bir dosyayı açar ve uzunluğu sıfır kendisine keser; Dosya yazma iznine sahip olmalıdır. İle belirtilemez **_O_RDONLY**. **_O_TRUNC** ile kullanılan **_O_CREAT** varolan bir dosyayı açar veya bir dosya oluşturur. **Not:** **_O_TRUNC** bayrağı belirtilen dosyanın içeriğini yok eder.
**_O_WRONLY**|Yalnızca yazmak için bir dosya açar. İle belirtilemez **_O_RDONLY** veya **_O_RDWR**.
**_O_U16TEXT**|Unicode UTF-16 modunda bir dosya açar.
**_O_U8TEXT**|Unicode UTF-8 modunda bir dosya açar.
**_O_WTEXT**|Bir dosya Unicode modunda açar.

Dosya erişim modu belirtmek için ya da belirtmeniz gerekir **_O_RDONLY**, **_O_RDWR**, veya **_O_WRONLY**. Erişim modu için varsayılan değer yoktur.

Ne zaman bir dosya açıldığında Unicode modunda kullanarak **_O_WTEXT**, **_O_U8TEXT**, veya **_O_U16TEXT**, giriş işlevleri Çevir UTF-16 verileri dosyadan okunan veriler türü olarak depolanan **wchar_t**. Unicode modunda açılan bir dosyaya yazma işlevleri beklediğiniz UTF-16 veri türü olarak depolanan içeren arabellek **wchar_t**. UTF-8 kodlanmış dosyası, ardından UTF-16 verileri UTF-8 yazılması ve okunduğunda, bu dosyanın içeriğini UTF-8 olarak kodlanmış UTF-16 çevrilir çevrilir. Girişimi okumak veya tek sayıda bayt Unicode modunda yazmak için bir parametre doğrulama hatasına neden olur. Programınız UTF-8 olarak depolanan verileri okuma veya yazma için bir Unicode modunda yerine bir metin veya ikili dosya modu kullanın. Tüm gerekli kodlama çeviri için sorumlu olursunuz.

Varsa **_sopen** çağrılır **_O_WRONLY** | **_O_APPEND** (ekleme modu) ve **_O_WTEXT**, **_O_ U16TEXT**, veya **_O_U8TEXT**, ilk çalıştığında dosyası okuma ve yazma için açılamadı ÜR okuyun ve ardından yalnızca yazmak için yeniden açın. Dosya başarısız yazma ve okuma için açılırken, yalnızca yazmak için dosyayı açar ve varsayılan değer Unicode modu ayarını kullanır.

Bağımsız değişken *shflag* Şunda tanımlı olan aşağıdaki bildirim sabitlerinden birini içeren sabit bir ifade \<share.h >.

|*shflag* sabit|Davranış|
|-|-|
**_SH_DENYRW**|Okuma ve dosyaya yazma erişimi engeller.
**_SH_DENYWR**|Bir dosyaya yazma erişimi engeller.
**_SH_DENYRD**|Bir dosya için okuma erişimi engeller.
**_SH_DENYNO**|İzin verir, okuma ve yazma erişimi.

*Pmode* bağımsız değişkeni gereklidir yalnızca **_O_CREAT** belirtilir. Dosya mevcut değilse *pmode* ilk kez yeni dosya kapatıldığında, ayarlanan dosyanın izin ayarlarını belirtir. Aksi takdirde, *pmode* göz ardı edilir. *pmode* birini veya ikisini de bildirim sabitleri içeren bir tamsayı ifade **_s_ıwrıte** ve **_s_ıread**, içinde tanımlandığı \<sys\stat.h >. Her iki sabitleri verildiğinde, bit düzeyinde OR işleci ile birleştirilir. Anlamını *pmode* gibidir.

|*pmode*|Açıklama|
|-|-|
**_S_IREAD**|Yalnızca okuma izin verilir.
**_S_IWRITE**|Yazma izin verilir. (Aslında, okuma ve yazma verir.)
**_S_IREAD** &AMP;#124; **_S_IWRITE**|Okuma ve yazma izin verilir.

Yazma izni verilmemişse, dosyanın salt okunur. Windows işletim sisteminde, tüm dosyaları okunabilir; Salt yazma izni vermek mümkün değildir. Bu nedenle, modları **_s_ıwrıte** ve **_s_ıread** | **_s_ıwrıte** eşdeğerdir.

**_sopen** geçerli dosya izni maskesi geçerli *pmode* önce izinleri ayarlayın. (Bkz [_umask](umask.md).)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_sopen**|\<io.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >, \<share.h >|
|**_wsopen**|\<io.h > veya \<wchar.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >, \<share.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_locking](locking.md).

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
