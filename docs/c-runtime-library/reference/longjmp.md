---
title: longjmp
ms.date: 08/14/2018
api_name:
- longjmp
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- longjmp
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: b4527a29475f9e393dc5abf19b866d926bec2ccc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953137"
---
# <a name="longjmp"></a>longjmp

Bir `setjmp` çağrı tarafından ayarlanan yığın ortamını ve yürütme yerel ayarını geri yükler.

## <a name="syntax"></a>Sözdizimi

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>Parametreler

*env*<br/>
Ortamın depolandığı değişken.

*value*<br/>
`setjmp` Çağrıya döndürülecek değer.

## <a name="remarks"></a>Açıklamalar

**Longjmp** işlevi, daha önce *env* tarafından `setjmp`daha önce kaydedilen bir yığın ortamını ve yürütme yerel ayarını geri yükler. `setjmp`ve **longjmp** , yerel olmayan bir **goto**yürütmek için bir yol sağlar; Genellikle, normal çağrı ve dönüş kuralları kullanılmadan, daha önce çağrılan bir yordamın hata işleme veya kurtarma koduna yürütme denetimini geçirmek için kullanılır.

' A yapılan `setjmp` çağrı, geçerli yığın ortamının *env*'ye kaydedilmesine neden olur. Daha sonraki bir **longjmp** çağrısı, kaydedilen ortamı geri yükler ve denetimi ilgili çağrının hemen ardından gelen `setjmp` noktaya döndürür. Yürütme, `setjmp` *değer* çağrı tarafından döndürülmüş gibi devam eder. Yordam alma denetimi tarafından erişilebilen tüm değişkenlerin (yazmaç değişkenleri hariç) değerleri, **longjmp** çağrıldığında sahip oldukları değerleri içerir. Kayıt değişkenlerinin değerleri tahmin edilemez. Tarafından `setjmp` döndürülen değer sıfırdan farklı olmalıdır. *Değer* 0 olarak geçirilirse, 1 değeri gerçek dönüşte değiştirilir.

**Microsoft 'a özgü**

Windows 'daki C++ Microsoft kodunda, **longjmp** , özel durum işleme kodu olarak aynı yığın geri sarma semantiğini kullanır. C++ Özel durumların ortaya çıkarılan aynı yerlerde kullanılması güvenlidir. Ancak, bu kullanım taşınabilir değildir ve bazı önemli uyarılarla birlikte gelir.

Yalnızca **longjmp** ' i çağıran işlevden `setjmp` önce çağırın; Aksi takdirde sonuçlar tahmin edilemez.

**Longjmp**kullanırken aşağıdaki kısıtlamalara uyun:

- Kayıt değişkenlerinin değerlerinin aynı kalacağından emin değildir. Çağırma `setjmp` yordamında kayıt değişkenlerinin değerleri, **longjmp** yürütüldükten sonra uygun değerlere geri yüklenemez.

- Kesme bir kayan nokta özel durumu nedeniyle kesintiye neden olmadığı takdirde bir kesme işleme yordamının denetimini aktarmak için **longjmp** kullanmayın. Bu durumda, bir program, [_fönayar](fpreset.md)çağırarak kayan nokta matematik paketini ilk kez yeniden başlattığında **longjmp** aracılığıyla bir kesme işleyicisinden dönebilir.

- Denetimi doğrudan veya dolaylı olarak Windows kodu tarafından çağrılan bir geri çağırma yordamından aktarmak için **longjmp** kullanmayın.

- Kod, **/EHS** veya **/EHsc** kullanılarak derlenirse ve **longjmp** çağrısını içeren işlev **noexcept** ise, bu işlevdeki yerel nesneler yığın geri alma sırasında parçalanmayabilir.

**SON Microsoft 'a özgü**

> [!NOTE]
> Taşınabilir C++ kodda, nesne semantiğini `setjmp` varsaymaz `longjmp` ve C++ destekleyebilirsiniz. Özellikle, `setjmp` **catch** ve **throw** / `longjmp` ile değiştirmek `setjmp` , tüm otomatik nesneler için önemsiz olmayan yıkıcıları çağıracağından, bir çağrı çiftinin tanımsız bir `longjmp` davranışı vardır. C++ Programlar ' da, C++ özel durum işleme mekanizmasını kullanmanızı öneririz.

Daha fazla bilgi için bkz. [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**longjmp**|\<setjmp. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Fönayar](fpreset.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)
