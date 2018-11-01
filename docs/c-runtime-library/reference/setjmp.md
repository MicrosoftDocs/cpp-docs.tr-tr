---
title: setjmp
ms.date: 08/14/2018
apiname:
- setjmp
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
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: 69af720c70393dbcad1e267b58e08876cdc2b77e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575072"
---
# <a name="setjmp"></a>setjmp

Programın geçerli durumunu kaydeder.

## <a name="syntax"></a>Sözdizimi

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>Parametreler

*Env*<br/>
Ortam depolandığı değişken.

## <a name="return-value"></a>Dönüş Değeri

Yığın ortamını kaydedildikten sonra 0 döndürür. Varsa **setjmp** sonucu olarak döndürür bir `longjmp` döndürür, çağrı *değer* bağımsız değişkeni `longjmp`, veya *değer* bağımsız değişkeni `longjmp` 0 ' dır **setjmp** 1 döndürür. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

**Setjmp** işlevi daha sonra kullanarak geri yükleyebileceğiniz bir yığın ortamı kaydeder `longjmp`. Birlikte kullanıldığında **setjmp** ve `longjmp` yerel olmayan yürütmek için bir yol sağlayan **goto**. Bunlar, genellikle normal arama kullanmadan daha önce çağrılmış bir yordam hata işleme veya kurtarma koduna yürütme denetimi geçirmek için kullanılan veya dönüş kuralları.

Bir çağrı **setjmp** geçerli yığın ortamda kaydeder *env*. Bir sonraki çağrı `longjmp` kaydedilmiş ortamını geri yükler ve döndürür denetim noktasına ilgili hemen sonra **setjmp** çağırın. Denetim alma yordamı için erişilebilir tüm değişkenleri (dışında kayıt değişkenleri) sahip oldukları zaman değerleri içeren `longjmp` çağrıldı.

Kullanmak mümkün değil **setjmp** yönetilen kod Yerelden atlamak için.

**Microsoft'a özgü**

Windows, Microsoft C++ kodu olarak **longjmp** aynı yığın geriye doğru izleme semantiği özel durum işleme kodu olarak kullanır. C++ özel durumlarını yükseltilebilir aynı yerde kullanmak daha güvenlidir. Ancak, bu kullanım taşınabilir değildir ve bazı önemli uyarılar ile birlikte gelir. Ayrıntılar için bkz [longjmp](longjmp.md).

**END Microsoft özgü**

> [!NOTE]
> Taşınabilir C++ kodunda, varsayamazsınız `setjmp` ve `longjmp` C++ nesnesi semantiğini destekler. Özellikle, bir `setjmp` / `longjmp` çifti tanımsız davranış değiştirerek, çağrı `setjmp` ve `longjmp` tarafından **catch** ve **throw** çağırır Otomatik nesneler için tüm önemsiz yok ediciler. C++ programlarında C++ özel durum işleme mekanizmasını kullanmanız önerilir.

Daha fazla bilgi için [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setjmp**|\<setjmp.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_fpreset](fpreset.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)
