---
title: _sopen, _wsopen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e8d7f7624dc8c521186aa697ad8825c77e0108f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418111"
---
# <a name="sopen-wsopen"></a>_sopen, _wsopen

Bir dosya paylaşımı için açılır. Bu işlevlerin daha güvenli sürümü: bkz [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md).

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
İzin verilen işlem türü.

*shflag*<br/>
İzin verilen paylaşım türü.

*pmode*<br/>
İzni ayarı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, açılan dosya için dosya tanımlayıcısı döndürür.

Varsa *filename* veya *oflag* olan bir **NULL** işaretçisi veya *oflag* veya *shflag* içinde geçerli değil aralık değerleri, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** aşağıdaki değerlerden birine.

|errno değeri|Koşul|
|-|-|
**EACCES**|Belirtilen yol bir dizin olduğundan veya dosya salt okunur durumdadır, ancak yazma için açık işlem yapılmaya çalışıldı.
**EEXIST**|**_O_CREAT** ve **_O_EXCL** bayrakları belirtildi, ancak *filename* zaten mevcut.
**EINVAL**|Geçersiz *oflag* veya *shflag* bağımsız değişkeni.
**EMFILE**|Daha fazla hiçbir dosya tanımlayıcıları kullanılabilir.
**ENOENT**|Dosya veya yol bulunamadı.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Sopen** işlev tarafından belirtilen dosyayı açar *filename* tarafından tanımlanan dosya paylaşılan okuma veya yazma için hazırlar *oflag* ve *shflag* . **_wsopen** bir joker karakter sürümü **_sopen**; *filename* bağımsız değişkeni **_wsopen** bir joker karakter dizesidir. **_wsopen** ve **_sopen** Aksi takdirde aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen**|**_sopen**|**_sopen**|**_wsopen**|

Tamsayı ifade *oflag* bir veya daha fazla tanımlanan aşağıdaki bildirim sabitleri birleştirerek biçimlendirilmiş \<fcntl.h >. Ne zaman iki veya daha fazla sabitleri form bağımsız değişkeni *oflag*, bit düzeyinde OR işleci ile birleştirilir ( **&#124;** ).

|*oflag* sabit|Davranış|
|-|-|
**_O_APPEND**|Dosya işaretçisini her yazma işleminden önce dosyanın sonuna taşır.
**_O_BINARY**|Dosya ikili (untranslated) modunda açılır. (Bkz [fopen](fopen-wfopen.md) ikili mod açıklaması.)
**_O_CREAT**|Bir dosya oluşturur ve yazma için açar. Dosyanın belirtilen etkisizdir *filename* bulunmaktadır. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT** &AMP;#124; **_O_SHORT_LIVED**|Dosya geçici olarak oluşturur ve mümkünse diske temizleme değil. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT** &AMP;#124; **_O_TEMPORARY**|Geçici olarak bir dosya oluşturur; son dosya tanımlayıcısı kapatıldığında dosya silinir. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT**&AMP;#124; ` _O_EXCL`|Bir hata değeri tarafından belirtilen bir dosya varsa döndürür *filename* bulunmaktadır. Yalnızca ile kullanıldığında geçerlidir **_O_CREAT**.
**_O_NOINHERIT**|Paylaşılan dosya tanımlayıcısı oluşturulmasını engeller.
**_O_RANDOM**|Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, için rasgele erişim diskten sınırlı gerekmez olduğunu belirtir.
**_O_RDONLY**|Yalnızca okumak için bir dosyayı açar. İle belirtilemez **_O_RDWR** veya **_O_WRONLY**.
**_O_RDWR**|Hem okumak ve yazmak için bir dosyayı açar. İle belirtilemez **_O_RDONLY** veya **_O_WRONLY**.
**_O_SEQUENTIAL**|Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, sıralı erişim için diskten sınırlı gerekmez olduğunu belirtir.
**_O_TEXT**|Bir dosya (çevrilmiş) metin modunda açılır. (Daha fazla bilgi için bkz: [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](fopen-wfopen.md).)
**_O_TRUNC**|Bir dosyayı açar ve onu uzunluğu sıfır olarak keser; Dosya yazma iznine sahip olmalıdır. İle belirtilemez **_O_RDONLY**. **_O_TRUNC** ile kullanılan **_O_CREAT** varolan bir dosyayı açar veya bir dosya oluşturur. **Not:** **_O_TRUNC** bayrağı belirtilen dosyanın içeriğini yok eder.
**_O_WRONLY**|Yalnızca yazmak için bir dosyayı açar. İle belirtilemez **_O_RDONLY** veya **_O_RDWR**.
**_O_U16TEXT**|Bir dosya Unicode UTF-16 modunda açılır.
**_O_U8TEXT**|Bir dosya Unicode UTF-8 modunda açılır.
**_O_WTEXT**|Bir dosya Unicode modunda açılır.

Dosya erişim modu belirtmek için ya da belirtmelisiniz **_O_RDONLY**, **_O_RDWR**, veya **_O_WRONLY**. Erişim modu için varsayılan değer yoktur.

Ne zaman bir dosya açıldığında Unicode modunda kullanarak **_O_WTEXT**, **_O_U8TEXT**, veya **_O_U16TEXT**, giriş işlevleri Çevir UTF-16 verisine dosyadan okunan veriler türü olarak depolanan **wchar_t**. Unicode modunda açılmış bir dosyaya yazma işlevleri beklediğiniz UTF-16 veri türü olarak depolanan içeren arabellekleri **wchar_t**. Dosyanın UTF-8 olarak kodlanmıştır, sonra UTF-16 verileri UTF-8 yazılması ve onu okunduğunda dosyanın içeriğini UTF-8 kodlu UTF-16 çevrilir çevrilir. Okuma veya tek sayıda bayt Unicode modda yazma girişiminde bir parametre doğrulama hatasına neden olur. Okumak veya programınız UTF-8 olarak depolanan veri yazmak için bir metin veya ikili dosya modu yerine Unicode modunu kullanın. Tüm gerekli kodlama çeviri sorumlu.

Varsa **_sopen** çağrılır **_O_WRONLY** | **_O_APPEND** (ekleme modu) ve **_O_WTEXT**, **_O_ U16TEXT**, veya **_O_U8TEXT**, ilk kez çalıştığında okuma ve yazma, dosyayı açmak ürün reçetesi okuyun ve sonra da yalnızca yazmak için kapatıp yeniden açın. Okuma ve yazma başarısız için dosyayı açmayı, yalnızca yazmak için dosyayı açar ve Unicode modu ayarı için varsayılan değeri kullanır.

Bağımsız değişken *shflag* tanımlanan aşağıdaki bildirim sabitlerden biri oluşan sabit bir ifade \<share.h >.

|*shflag* sabit|Davranış|
|-|-|
**_SH_DENYRW**|Bir dosya için okuma ve yazma reddeder.
**_SH_DENYWR**|Dosyaya yazma erişimini engeller.
**_SH_DENYRD**|Dosyaya okuma erişimini engeller.
**_SH_DENYNO**|İzinleri okuma ve yazma erişimi.

*Pmode* bağımsız değişkeni gereklidir yalnızca **_O_CREAT** belirtilir. Dosya mevcut değilse *pmode* yeni dosya ilk kez kapatıldığında ayarlanan dosyanın izin ayarları, belirtir. Aksi takdirde, *pmode* göz ardı edilir. *pmode* birini veya her ikisini bildirim sabitleri içeren bir tamsayı ifade **_s_ıwrıte** ve **_s_ıread**, içinde tanımlanan \<sys\stat.h >. Her iki sabitleri verildiğinde, bunlar bit düzeyinde OR işleci ile birleştirilir. Anlamını *pmode* aşağıdaki gibidir.

|*pmode*|Açıklama|
|-|-|
**_S_IREAD**|Yalnızca okuma izin verilir.
**_S_IWRITE**|Yazma izin verilir. (Geçerli, okuma ve yazma izin verir.)
**_S_IREAD** &AMP;#124; **_S_IWRITE**|Okuma ve yazma izin verilir.

Yazma izni verilmedi, dosya salt okunurdur. Windows işletim sisteminde, tüm dosyaları okunabilir; salt yazılır izin vermek mümkün değildir. Bu nedenle, modları **_s_ıwrıte** ve **_s_ıread** | **_s_ıwrıte** eşdeğerdir.

**_sopen** geçerli dosya izni maskesi uygular *pmode* önce izinleri ayarlayın. (Bkz [_umask](umask.md).)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_sopen**|\<io.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >, \<share.h >|
|**_wsopen**|\<io.h > veya \<wchar.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >, \<share.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_locking](locking.md).

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
