---
title: mbsrtowcs
ms.date: 11/04/2016
apiname:
- mbsrtowcs
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsrtowcs
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 2bc0c8c9e2d871b6d1748c42dc02c627244dbf69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597151"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

Çok baytlı karakter dizesi geçerli ayardaki ortasında bir çok baytlı karakterin yeniden özelliğine karşılık gelen bir geniş karakter dizesi dönüştürür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [mbsrtowcs_s](mbsrtowcs-s.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*wcstr*<br/>
Ortaya çıkan dönüştürülmüş geniş karakter dizesi depolamak için adres.

*mbstr*<br/>
Dönüştürülecek çok baytlı karakter dizesi konumunu dolaylı işaretçisi.

*Sayısı*<br/>
Dönüştürmek ve depolamak için (aynı zamanda bayt değil) karakter sayısı *wcstr*.

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** dönüştürme durum nesnesi. Bu değer bir null işaretçi ise, statik iç dönüştürme durum nesnesi kullanılır. Olduğundan iç **mbstate_t** nesne iş parçacığı güvenli değil, size her zaman kendi geçmesini öneririz *mbstate* parametresi.

## <a name="return-value"></a>Dönüş Değeri

Sondaki null karakter varsa içermeden başarıyla dönüştürüldü, karakter sayısını döndürür. Döndürür (bir hata oluştu ve ayarlar size_t)(-1) **errno** EILSEQ için.

## <a name="remarks"></a>Açıklamalar

**Mbsrtowcs** işlevi dönüştürür bir dolaylı olarak işaret ettiği çok baytlı karakter dizesi *mbstr*, işaret ettiği arabellek içinde depolanan geniş karakterlerin içine *wcstr*tarafından içindeki dönüştürme durumu kullanarak *mbstate*. Ya da bir sonlandırıcı null karakterin karşılaşılanaa kadar dönüştürme her karakter için geçerli yerel ayarı geçerli bir karakter gelmiyor çok baytlı bir dizisi karşılaştı, eder veya kadar *sayısı* karakter dönüştürüldü. Varsa **mbsrtowcs** çok baytlı null karakteri ('\0') önce veya ne zaman karşılaştığında *sayısı* gerçekleşir dönüştürür, 16 bit sondaki boş karakter ve durur.

Bu nedenle, geniş karakter dizesi *wcstr* yalnızca aşağıdaki durumlarda sonlandırılmış **mbsrtowcs** dönüştürme sırasında bir null karakterin karşılaşır. Dizileri işaret ettiği varsa *mbstr* ve *wcstr* üst üste, davranışını **mbsrtowcs** tanımsızdır. **mbsrtowcs** geçerli yerel ayarı LC_TYPE kategoriye göre etkilenir.

**Mbsrtowcs** işlevi farklıdır [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) kendi restartability tarafından. Dönüştürme durumunu depolanan *mbstate* aynı ya da yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar için. Yeniden başlatılabilir ve nonrestartable işlevlerin kullanımını kullanırken sonuçlar tanımsızdır.  Örneğin, bir uygulamanın kullanması gereken **mbsrlen** yerine **mbslen**sonraki çağrı, **mbsrtowcs** yerine kullanılan **mbstowcs**.

Varsa *wcstr* null bir işaretçi değil işaretçi nesnesinin tarafından işaret edilen *mbstr* null bir işaretçi bir sonlandırıcı null karakter üst sınırına ulaşıldığından dönüştürme durdurduysanız atanır. Aksi takdirde, varsa, son çok baytlı karakter dönüştürülür, adresi yalnızca geçmiş atanır. Bu, bir sonraki işlev çağrısı dönüştürme yeniden başlatmak bu çağrı durduğu sağlar.

Varsa *wcstr* bağımsız değişken null bir işaretçi ise *sayısı* bağımsız değişkeni yoksayılır ve **mbsrtowcs** geniş karakter hedef dizesi için gerekli boyutu döndürür. Varsa *mbstate* null bir işaretçiyse, iş parçacığı güvenli statik iç işlevini kullanan **mbstate_t** dönüştürme durum nesnesi. Varsa karakter dizisi *mbstr* karşılık gelen bir çok baytlı yok karakter gösterimi, -1 döndürülür ve **errno** ayarlanır **EILSEQ**.

Varsa *mbstr* ISA null işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve -1 döndürür.

C++'da, bu işlev bu işlevin daha yeni ve güvenli karşılığı çağıran bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Mbsrtowcs** işlevi, geçerli iş parçacığındaki hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu **setlocale** bu işlev yürütülürken sürece ve *mbstate* bağımsız değişken null bir işaretçi değil.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
