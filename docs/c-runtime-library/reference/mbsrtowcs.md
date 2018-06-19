---
title: mbsrtowcs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccb5bda16238888905678ffb3b6de01b93555ad0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405438"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

Çok baytlı karakter dizesi geçerli yerel birden çok baytlı karakter ortasında yeniden özelliği ile ilgili geniş karakter dizeye dönüştürür. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [mbsrtowcs_s](mbsrtowcs-s.md).

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
Dönüştürme için birden çok baytlı karakter dizesi konuma dolaylı işaretçi.

*Sayısı*<br/>
En fazla dönüştürmek ve depolamak için (bayt değil) karakter sayısını *wcstr*.

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** dönüştürme durum nesnesi. Bu değer null işaretçi ise, bir statik iç dönüştürme durumu nesnesi kullanılır. Çünkü iç **mbstate_t** nesnesi iş parçacığı açısından güvenli değil, her zaman kendi geçirdiğiniz olmasını öneririz *mbstate* parametresi.

## <a name="return-value"></a>Dönüş Değeri

Sonlandırma null karakteri varsa hariç başarıyla dönüştürüldü karakterlerin sayısını döndürür. Döndürür (bir hata oluştu ve ayarlar size_t)(-1) **errno** EILSEQ için.

## <a name="remarks"></a>Açıklamalar

**Mbsrtowcs** işlevi dönüştürür dolaylı olarak gösterdiği birden çok baytlı karakter dizesi *mbstr*, geniş karakterler gösterdiği arabellek depolanan içine *wcstr*, göre bulunan dönüştürme durumunu kullanarak *mbstate*. Ya da bir sonlandırma null birden çok baytlı karakter karşılaşılana kadar dönüştürme her bir karakter için geçerli bir karakter geçerli yerel karşılık gelmiyor birden çok baytlı bir dizisi hatayla karşılaşıldı, devam veya kadar *sayısı* karakter dönüştürüldü. Varsa **mbsrtowcs** birden çok baytlı null karakteri ('\0') önce veya ne zaman karşılaşırsa *sayısı* oluşur, dönüştürür, 16 bit sonlandırma null karakter ve durdurur.

Bu nedenle, geniş karakter dizesini *wcstr* null-yalnızca sonlandırılır **mbsrtowcs** birden çok baytlı bir null karakter dönüştürme sırasında karşılaşır. Dizileri gösterdiği varsa *mbstr* ve *wcstr* üst üste, davranışını **mbsrtowcs** tanımlanmadı. **mbsrtowcs** geçerli yerel LC_TYPE kategoriye göre etkilenir.

**Mbsrtowcs** işlevi farklı olarak [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan *mbstate* sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış.  Örneğin, bir uygulama kullanması gereken **mbsrlen** yerine **mbslen**, bir sonraki çağrı, **mbsrtowcs** yerine kullanılan **mbstowcs**.

Varsa *wcstr* null işaretçinin değil tarafından işaretçi nesne işaret için *mbstr* sonlandırma bir null karakter ulaştığından dönüştürme durdurduysanız null işaretçi atanır. Aksi takdirde, varsa, son birden çok baytlı karakter dönüştürülür, adresi yalnızca geçmiş atanır. Bu, bir sonraki işlev çağrısı dönüştürme yeniden başlatmak bu çağrıyı durduğu sağlar.

Varsa *wcstr* bağımsız değişkeni olan bir null işaretçinin *sayısı* bağımsız değişkeni göz ardı edilir ve **mbsrtowcs** gereken boyut geniş karakterler hedef dize döndürür. Varsa *mbstate* null işaretçi, iç iş parçacığı güvenli olmayan statik işlevini kullanıyor **mbstate_t** dönüştürme durum nesnesi. Varsa bir karakter dizisi *mbstr* karşılık gelen çok baytlı yok karakter gösterimi, -1 döndürülür ve **errno** ayarlanır **EILSEQ**.

Varsa *mbstr* ISA null işaretçinin, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve -1 döndürür.

C++'da, bu işlev bu işlevin yeni, güvenli karşılık gelen çağıran bir şablon aşırı sahiptir. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Mbsrtowcs** işlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu **setlocale** bu işlevi çalıştırma sürece ve *mbstate* bağımsız değişken null işaretçi değil.

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
