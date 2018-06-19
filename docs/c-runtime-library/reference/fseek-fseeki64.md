---
title: fseek, _fseeki64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fseeki64
- fseek
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a327bf196da71f47262c957e7fe6a8352971c36d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403748"
---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64

Dosya işaretçisini belirtilen bir konuma taşır.

## <a name="syntax"></a>Sözdizimi

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

*uzaklık*<br/>
Bayt sayısı *kaynak*.

*Kaynak*<br/>
Başlangıç konumu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fseek** ve **_fseeki64** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür. Cihazlarda aramayı kuramadığı dönüş değeri tanımlanmamıştır. Varsa *akış* null işaretçinin veya *kaynak* aşağıda açıklanan izin verilen değerlerden biri değil **fseek** ve **_fseeki64** geçersiz çağırma bölümünde açıklandığı gibi parametre işleyicisi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**Fseek** ve **_fseeki64** taşır (varsa) dosya işaretçisini ilişkili işlevleri *akış* yeni bir konuma *uzaklık* bayt, kaynağı *kaynak*. Sonraki işlem akışını yeni konumda gerçekleşir. Güncelleştirme için açık bir akış üzerinde okuma veya yazma sonraki işlemi olabilir. Bağımsız değişken *kaynak* STDIO içinde tanımlanan sabitlerden biri olması gerekir. Y:

|Kaynak değeri|Açıklama|
|-|-|
**SEEK_CUR**|Dosya işaretçisini geçerli konumu.
**SEEK_END**|Dosya sonu.
**SEEK_SET**|Dosya başlangıcı.

Kullanabileceğiniz **fseek** ve **_fseeki64** işaretçi bir dosyada herhangi bir yere yeniden konumlandırmak için. İşaretçinin dosyanın sonunu aşan konumlandırılmış olabilir. **fseek** ve **_fseeki64** dosya sonu göstergesi temizler ve tüm önceki etkisini geçersiz hale getirir [ungetc](ungetc-ungetwc.md) karşı çağırır *akış*.

Veri ekleme için bir dosya açıldığında, geçerli dosya konumu değil burada sonraki yazma oluşacak tarafından son g/ç işlemi tarafından belirlenir. G/ç işlemi henüz ekleme için açılan bir dosyada oluştuysa, dosya konumu dosya sayısıdır.

Metin modunda açılmış akışlar için **fseek** ve **_fseeki64** kullanımı, satır başı satır besleme çevirileri neden olabileceği için sınırlı **fseek** ve **_ fseeki64** beklenmeyen sonuçlar üretmek için. Yalnızca **fseek** ve **_fseeki64** metin modunda açılmış akışları üzerinde çalışmak için garanti işlemleri:

- Uzaklığı 0 kaynak değerlerden herhangi birine göre ile aramayı.

- Bir uzaklık değeri dosyasıyla başından itibaren aramayı döndürülen çağrısından [ftell](ftell-ftelli64.md) kullanırken **fseek** veya [_ftelli64](ftell-ftelli64.md) kullanırken **_fseeki64**.

Ayrıca metin modunda, CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılmış dosyalarında [fopen](fopen-wfopen.md) ve tüm ilgili yordamlar için CTRL + Z dosyanın sonunda denetleyin ve mümkünse kaldırın. Bu birleşimini kullanarak yapılır, çünkü **fseek** ve [ftell](ftell-ftelli64.md) veya **_fseeki64** ve [_ftelli64](ftell-ftelli64.md)ile biten bir dosya içinde taşımak için CTRL + Z neden olabilecek **fseek** veya **_fseeki64** dosyanın sonuna yakın yanlış bir şekilde davranır.

CRT bir bayt sırası işareti (BOM) ile başlayan bir dosyayı açtığında dosya işaretçisini sonra AĞACI konumlandırılır (diğer bir deyişle, dosyanın gerçek içeriği başlangıcında). Gerekirse **fseek** dosyasının başlangıcına kullanmak [ftell](ftell-ftelli64.md) ilk konumunu almak için ve **fseek** ona yerine 0 konumuna.

Bu işlev yürütülürken başka bir iş parçacığı kilitler ve bu nedenle iş parçacığı. Kilitleme olmayan bir sürümü için bkz: [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fseek**|\<stdio.h >|
|**_fseeki64**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
