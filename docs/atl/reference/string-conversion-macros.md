---
title: Dize Dönüşüm Makroları
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: 8df496b78334d26e7d3664642b2e9d93d6149843
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325849"
---
# <a name="string-conversion-macros"></a>Dize Dönüşüm Makroları

Bu makrolar dize dönüştürme özellikleri sağlar.

## <a name="atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a>ATL ve MFC String Dönüşüm Makroları

Burada tartışılan dize dönüştürme makroları hem ATL hem de MFC için geçerlidir. MFC dize dönüştürme hakkında daha fazla bilgi için [bkz: TN059: MFC MBCS/Unicode Dönüşüm Makroları](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) ve [MFC Makroları ve Globaller](../../mfc/reference/mfc-macros-and-globals.md)kullanma.

## <a name="devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE ve TEXTMETRIC String Dönüşüm Makroları

Bu [makrolar, DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veya [TEXTMETRIC](/windows/win32/api/wingdi/ns-wingdi-textmetricw) yapısının bir kopyasını oluşturur ve yeni yapıdaki dizeleri yeni bir dize türüne dönüştürür. Makrolar yeni yapı için yığında bellek ayırır ve yeni yapıya bir işaretçi döndürün.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Açıklamalar

Örneğin:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

ve:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

Makro adlarında, kaynak yapıdaki dize türü soldadır (örneğin, **A)** ve hedef yapıdaki dize türü sağdadır (örneğin, **W).** **LPSTR,** **OLE** LPOLESTR, **T** LPTSTR ve **W** LPWSTR anlamına gelir anlamına gelir.

Böylece, DEVMODEA2W LPWSTR dizeleri ile bir yapı içine LPSTR dizeleri ile `DEVMODE` bir `DEVMODE` yapı `TEXTMETRIC` kopyalar, TEXTMETRICOLE2T LPTSTR dizeleri ile bir `TEXTMETRIC` yapı içine LPOLESTR dizeleri ile bir yapı kopyalar, ve benzeri.

`DEVMODE` Yapıda dönüştürülen iki dize aygıt adı`dmDeviceName`( ) ve`dmFormName`form adı ( ). Dize `DEVMODE` dönüştürme makroları da yapı`dmSize`boyutunu güncelleştirin ( ).

`TEXTMETRIC` Yapıda dönüştürülen dört dize ilk karakter`tmFirstChar`( ),`tmLastChar`son karakter (`tmDefaultChar`), varsayılan karakter`tmBreakChar`( ), ve kesme karakteridir .

Ve `TEXTMETRIC` dize `DEVMODE` dönüştürme makrolarının davranışı, varsa, etkin olan derleyici yönergesi bağlıdır. Kaynak ve hedef türleri aynıysa, dönüşüm gerçekleşmez. Derleyici yönergeleri **T** ve **OLE'yi** aşağıdaki gibi değiştirir:

|Derleyici yönergesi yürürlükte|T olur|OLE olur|
|----------------------------------|---------------|-----------------|
|yok|**A**|**W**|
|**\_Unicode**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|UNICODE ve **OLE2ANSI** ** \_**|**W**|**A**|

Aşağıdaki tabloda `DEVMODE` ve `TEXTMETRIC` dize dönüştürme makroları listelenir.

|||
|-|-|
|DEVMODEA2W|TEKSTİlMETRICA2W|
|DEVMODEOLE2T|TEKSTİlMETRICOLE2T|
|DEVMODET2OLE|TEKSTİlMETRICT2OLE|
|DEVMODEW2A|TEKSTİlMEW2A|

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
