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
ms.openlocfilehash: 4f737818afe7136262362e4fe996745064568758
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218565"
---
# <a name="longjmp"></a>longjmp

Bir çağrı tarafından ayarlanan yığın ortamını ve yürütme yerel ayarını geri yükler `setjmp` .

## <a name="syntax"></a>Söz dizimi

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>Parametreler

*env*<br/>
Ortamın depolandığı değişken.

*deeri*<br/>
Çağrıya döndürülecek değer `setjmp` .

## <a name="remarks"></a>Açıklamalar

**Longjmp** işlevi, daha önce *env* tarafından daha önce kaydedilen bir yığın ortamını ve yürütme yerel ayarını geri yükler `setjmp` . `setjmp`ve **longjmp** , yerel olarak yürütmek için bir yol sağlar **`goto`** ; genellikle yürütme denetimini, normal çağrı ve dönüş kuralları kullanılmadan daha önce çağrılan bir yordamın hata işleme veya kurtarma koduna geçirmek için kullanılır.

' A yapılan çağrı `setjmp` , geçerli yığın ortamının *env*'ye kaydedilmesine neden olur. Daha sonraki bir **longjmp** çağrısı, kaydedilen ortamı geri yükler ve denetimi ilgili çağrının hemen ardından gelen noktaya döndürür `setjmp` . Yürütme, *değer* çağrı tarafından döndürülmüş gibi devam eder `setjmp` . Yordam alma denetimi tarafından erişilebilen tüm değişkenlerin (yazmaç değişkenleri hariç) değerleri, **longjmp** çağrıldığında sahip oldukları değerleri içerir. Kayıt değişkenlerinin değerleri tahmin edilemez. Tarafından döndürülen değer `setjmp` sıfırdan farklı olmalıdır. *Değer* 0 olarak geçirilirse, 1 değeri gerçek dönüşte değiştirilir.

**Microsoft'a Özgü**

Windows 'daki Microsoft C++ kodunda, **longjmp** , özel durum işleme kodu olarak aynı yığın geri sarma semantiğini kullanır. C++ özel durumlarının ortaya çıkarılan aynı yerlerde kullanılması güvenlidir. Ancak, bu kullanım taşınabilir değildir ve bazı önemli uyarılarla birlikte gelir.

Yalnızca **longjmp** ' i çağıran işlevden önce çağırın `setjmp` ; Aksi takdirde sonuçlar tahmin edilemez.

**Longjmp**kullanırken aşağıdaki kısıtlamalara uyun:

- Kayıt değişkenlerinin değerlerinin aynı kalacağından emin değildir. Çağırma yordamında kayıt değişkenlerinin değerleri, `setjmp` **longjmp** yürütüldükten sonra uygun değerlere geri yüklenemez.

- Kesme bir kayan nokta özel durumu nedeniyle kesintiye neden olmadığı takdirde bir kesme işleme yordamının denetimini aktarmak için **longjmp** kullanmayın. Bu durumda, bir program, [_fpreset](fpreset.md)çağırarak kayan nokta matematik paketini ilk kez yeniden başlattığında **longjmp** aracılığıyla bir kesme işleyicisinden dönebilir.

- Denetimi doğrudan veya dolaylı olarak Windows kodu tarafından çağrılan bir geri çağırma yordamından aktarmak için **longjmp** kullanmayın.

- Kod, **/EHS** veya **/EHsc** kullanılarak derlenmişse ve **longjmp** çağrısını içeren işlev ise, **`noexcept`** Bu işlev içindeki yerel nesneler, yığın geriye doğru şekilde parçalanmayabilir.

**SON Microsoft 'a özgü**

> [!NOTE]
> Taşınabilir C++ kodunda, `setjmp` `longjmp` C++ nesne semantiğini varsaymaz ve destekleyebilirsiniz. Özellikle, bir `setjmp` / `longjmp` çağrı çiftinin, ve ile değiştiriyorsanız tanımsız bir davranışı vardır `setjmp` `longjmp` **`catch`** ve **`throw`** herhangi bir otomatik nesne için tüm önemsiz olmayan yıkıcıları çağırır. C++ programlarında, C++ özel durum işleme mekanizmasını kullanmanızı öneririz.

Daha fazla bilgi için bkz. [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**longjmp**|\<setjmp.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Fpreset](fpreset.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)
