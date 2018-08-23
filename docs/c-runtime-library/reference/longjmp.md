---
title: longjmp | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- longjmp
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
- longjmp
dev_langs:
- C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 857fae2e9c38dfe2c5cd468c6d1b50c6fdd2f317
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42465748"
---
# <a name="longjmp"></a>longjmp

Yığın ortamını ve yürütme yerel ayarlarını geri yükler bir `setjmp` çağırın.

## <a name="syntax"></a>Sözdizimi

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>Parametreler

*Env*  
Ortam depolandığı değişken.

*value*  
İçin döndürülecek değer `setjmp` çağırın.

## <a name="remarks"></a>Açıklamalar

**Longjmp** işlevi geri yükler, daha önce kaydedilmiş bir yığın ortamını ve yürütme yerel *env* tarafından `setjmp`. `setjmp` ve **longjmp** bir yerel olmayan yürütmek için bir yol sağlayan **goto**; bunlar genellikle normal çağrı kullanmadan daha önce çağrılmış bir yordam hata işleme veya kurtarma koduna yürütme denetimi geçirmek için kullanılır ve dönüş kuralları.

Bir çağrı `setjmp` kaydedilmesi geçerli yığın ortamını neden *env*. Bir sonraki çağrı **longjmp** kaydedilmiş ortamını geri yükler ve denetim noktasına karşılık gelen takip döndürür `setjmp` çağırın. Yürütme devam ettirir gibi *değer* tarafından yalnızca geri dönmüş `setjmp` çağırın. Denetim alma yordamı için erişilebilir (yazmaç değişkenleri dışında) tüm değişkenlerin değerlerini sahip oldukları zaman değerleri içeren **longjmp** çağrıldı. Kayıt değişkenlerin değerleri tahmin edilemez. Tarafından döndürülen değer `setjmp` sıfır olmalıdır. Varsa *değer* geçirilen 0 1 değeri gerçek dönüş konur.

**Microsoft'a özgü**

Windows, Microsoft C++ kodu olarak **longjmp** aynı yığın geriye doğru izleme semantiği özel durum işleme kodu olarak kullanır. C++ özel durumlarını yükseltilebilir aynı yerde kullanmak daha güvenlidir. Ancak, bu kullanım taşınabilir değildir ve bazı önemli uyarılar ile birlikte gelir.

Yalnızca çağrı **longjmp** çağıran işleve önce `setjmp` döndürür; Aksi takdirde sonuçlar tahmin edilemez.

Kullanırken aşağıdaki kısıtlamalar gözlemleyin **longjmp**:

- Kayıt değişkenlerin değerleri aynı şekilde kalır varsaymayın. Rutin arama kaydı değişkenlerin değerleri `setjmp` sonra uygun değerlere geri değil **longjmp** yürütülür.

- Kullanmayın **longjmp** denetimi bir kesme işleme yordamını dışında bir kayan nokta özel durumu kesintiye neden olmazsa aktarmak için. Bu durumda, bir program bir kesme işleyicisinden döndürebilir **longjmp** , ilk kayan nokta matematik paketindeki çağırarak yeniden başlatır, [_fpreset](fpreset.md).

- Kullanmayın **longjmp** doğrudan veya dolaylı olarak Windows kod tarafından çağrılan bir geri çağırma yordamı denetim aktarabilir.

- Kod kullanarak derlenirse **EHS** veya **/ehsc** ve içeren işlev **longjmp** çağrı **noexcept** sonra yerel nesneleri işlev yığın bırakma sırasında imha değil.

**END Microsoft özgü**

> [!NOTE]  
> Taşınabilir C++ kodunda, varsayamazsınız `setjmp` ve `longjmp` C++ nesnesi semantiğini destekler. Özellikle, bir `setjmp` / `longjmp` çifti tanımsız davranış değiştirerek, çağrı `setjmp` ve `longjmp` tarafından **catch** ve **throw** çağırır Otomatik nesneler için tüm önemsiz yok ediciler. C++ programlarında C++ özel durum işleme mekanizmasını kullanmanız önerilir.

Daha fazla bilgi için [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**longjmp**|\<setjmp.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_fpreset](fpreset.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)  
[setjmp](setjmp.md)  
