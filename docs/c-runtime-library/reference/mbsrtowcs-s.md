---
title: mbsrtowcs_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- mbsrtowcs_s
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
- mbsrtowcs_s
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc125521b7db7537ecbbf3fe3c42ec6b8b8e1ada
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="mbsrtowcss"></a>mbsrtowcs_s

Çok baytlı karakter dizesi geçerli yerel kendi geniş karakter dizesi gösterimine dönüştürür. Bir sürümünü [mbsrtowcs](mbsrtowcs.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t * wcstr,
   size_t sizeInWords,
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
);
template <size_t size>
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t (&wcstr)[size],
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*pReturnValue*<br/>
Dönüştürülen karakter sayısı.

*wcstr*<br/>
Elde edilen depolamak için arabellek adresini dönüştürülen geniş karakter dizesi.

*sizeInWords*<br/>
Boyutunu *wcstr* içinde sözcükleri (geniş karakter).

*mbstr*<br/>
Dönüştürülecek birden çok baytlı karakter dizesi konuma dolaylı işaretçi.

*Sayısı*<br/>
En fazla depolamak üzere geniş karakter sayısını *wcstr* arabellek, sonlandırma null dahil değil veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** dönüştürme durum nesnesi. Bu değer null işaretçi ise, bir statik iç dönüştürme durumu nesnesi kullanılır. Çünkü iç **mbstate_t** nesnesi iş parçacığı açısından güvenli değil, her zaman kendi geçirdiğiniz olmasını öneririz *mbstate* parametresi.

## <a name="return-value"></a>Dönüş Değeri

Dönüştürme başarılı olduğunda sıfır veya hatasında bir hata kodu.

|Hata durumu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* null işaretçi ve *sizeInWords* > 0|**EINVAL**|
|*mbstr* null işaretçi|**EINVAL**|
|Dize dolaylı olarak işaret için tarafından *mbstr* geçerli yerel ayar için geçerli olmayan bir birden çok baytlı dizisi içerir.|**EILSEQ**|
|Hedef arabellek dönüştürülmüş dizeyi içeren için çok küçük. (sürece *sayısı* olan **_TRUNCATE**; daha fazla bilgi için açıklamalar bakın)|**ERANGE**|

Bu koşulların herhangi biri meydana gelirse, geçersiz bir parametre özel durum açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu işlevi döndürür ve ayarlar **errno** tabloda belirtildiği şekilde.

## <a name="remarks"></a>Açıklamalar

**Mbsrtowcs_s** işlevi dönüştürür dolaylı olarak gösterdiği birden çok baytlı karakter dizesi *mbstr* gösterdiği arabellek depolanan geniş karakterler içine *wcstr*, göre bulunan dönüştürme durumunu kullanarak *mbstate*. Bu koşullardan biri yerine getirilene kadar dönüştürme için her karakter devam eder:

- Birden çok baytlı null karakteri ile karşılaşıldı

- Geçersiz bir birden çok baytlı karakter karşılaştı

- Depolanan geniş karakter sayısını *wcstr* arabellek eşittir *sayısı*.

Hedef dize *wcstr* null ile sonlandırılmış bir hata olması durumunda bile, her zaman olduğu sürece *wcstr* null işaretçi.

Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), **mbsrtowcs_s** dize olarak büyük dönüştürür hala null yer bırakarak hedef arabelleğine sığacak Sonlandırıcı.

Varsa **mbsrtowcs_s** başarıyla kaynak dizesi dönüştürür dönüştürülmüş dizeyi ve içine null Sonlandırıcı geniş karakter cinsinden boyutu koyar  *&#42;pReturnValue*, sağlanan  *pReturnValue* null işaretçi değil. Bu meydana olsa bile *wcstr* bağımsız değişkeni null işaretçi ve gerekli arabellek boyutunu belirlemenize olanak tanır. Unutmayın *wcstr* null işaretçi *sayısı* göz ardı edilir.

Varsa *wcstr* null işaretçinin değil tarafından işaretçi nesne işaret için *mbstr* sonlandırma bir null karakter ulaştığından dönüştürme durdurduysanız null işaretçi atanır. Aksi takdirde, varsa, son birden çok baytlı karakter dönüştürülür, adresi yalnızca geçmiş atanır. Bu, bir sonraki işlev çağrısı dönüştürme yeniden başlatmak bu çağrıyı durduğu sağlar.

Varsa *mbstate* null işaretçi, iç Kitaplığı **mbstate_t** dönüştürme durumu statik nesnesi kullanılır. Bu dahili statik nesnenin iş parçacığı olmadığı için kendi geçirmenizi öneririz *mbstate* değeri.

Varsa **mbsrtowcs_s** geçerli yerel ayarında geçersiz bir birden çok baytlı karakter karşılaştığında -1 koyar  *&#42;pReturnValue*, hedef arabelleği ayarlar *wcstr* boş bir dize olarak ayarlar **errno** için **EILSEQ**ve döndürür **EILSEQ**.

Dizileri gösterdiği varsa *mbstr* ve *wcstr* üst üste, davranışını **mbsrtowcs_s** tanımlanmadı. **mbsrtowcs_s** geçerli yerel LC_TYPE kategoriye göre etkilenir.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* çakışmaması ve *sayısı* doğru şekilde dönüştürmek için birden çok baytlı karakter sayısını yansıtır.

**Mbsrtowcs_s** işlevi farklı olarak [mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan *mbstate* sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış. Örneğin, bir uygulama kullanması gereken **mbsrlen** yerine **mbslen**, bir sonraki çağrı, **mbsrtowcs_s** yerine kullanılan **mbstowcs_s**.

C++'da, bu işlevi kullanarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeni belirtmeniz gerekliliğini ortadan) ve yeni, güvenli dekiler kullanarak bunlar daha eski, güvenli olmayan işlevleri otomatik olarak değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Mbsrtowcs_s** işlevi ise çoklu iş parçacığı güvenli bir işlev geçerli iş parçacığı çağrılarında **setlocale** bu işlevi çalıştırma sürece ve *mbstate* bağımsız değişkeni null bir işaretçi yok.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
