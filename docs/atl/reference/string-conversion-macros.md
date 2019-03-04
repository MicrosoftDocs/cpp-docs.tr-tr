---
title: Dize dönüşüm makroları
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
ms.openlocfilehash: 889f8459e81418197420bc2efd410225d4f220bc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271768"
---
# <a name="string-conversion-macros"></a>Dize dönüşüm makroları

Bu makroları, dize dönüştürme özellikleri sağlar.

##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL ve MFC dize dönüşüm makroları

Burada tartışılan dize dönüşüm makroları, ATL ve MFC için geçerlidir. MFC dize dönüştürme hakkında daha fazla bilgi için bkz. [TN059: MFC MBCS/Unicode dönüştürme makrolarını kullanma](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) ve [MFC makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md).

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  DEVMODE ve TEXTMETRIC dize dönüşüm makroları

Bu makrolar bir kopyasını oluşturmak bir [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) veya [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) yapısı ve dizeleri yeni yapısı içinde yeni bir dize türüne dönüştürün. Makrolar, yığında bellek ayırmak için yeni yapısı ve yeni yapısına bir işaretçi döndürür.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Açıklamalar

Örneğin:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

ve:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

Makrosu adlarında soldaki kaynak yapısı içinde dize türü olduğundan (örneğin, **A**) ve hedef yapısı içinde dize türü sağ tarafta ise (örneğin, **W**). **A** LPSTR için anlamına gelir **OLE** LPOLESTR için anlamına gelir **T** LPTSTR için anlamına gelir ve **W** LPWSTR için anlamına gelir.

DEVMODEA2W kopyalar. Bu nedenle, bir `DEVMODE` LPSTR yapısıyla dizeleri içine bir `DEVMODE` LPWSTR dizeleriyle TEXTMETRICOLE2T kopyaları yapısı bir `TEXTMETRIC` LPOLESTR yapısıyla dizeleri içine bir `TEXTMETRIC` LPTSTR dizelerle yapısı ve benzeri.

İki dizenin dönüştürülüp `DEVMODE` yapısı olan cihaz adını (`dmDeviceName`) ve form adı (`dmFormName`). `DEVMODE` Dize dönüşüm makroları, yapı boyutu da güncelleştirin (`dmSize`).

Dönüştürülüp dört dizeleri `TEXTMETRIC` yapısı ilk karakter olduğu (`tmFirstChar`), son karakter (`tmLastChar`), varsayılan karakter (`tmDefaultChar`) ve kesme karakteri (`tmBreakChar`).

Davranışını `DEVMODE` ve `TEXTMETRIC` dize dönüşüm makroları bağlıdır etkisi, derleyici yönergedeki varsa. Kaynak ve hedef türleri aynı ise, hiçbir dönüştürme gerçekleşir. Derleyici yönergeleri değiştirme **T** ve **OLE** gibi:

|Derleyici yönergesi efekti|T olur|OLE olur|
|----------------------------------|---------------|-----------------|
|yok|**A**|**W**|
|**\_UNICODE**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|**\_UNICODE** ve **OLE2ANSI**|**W**|**A**|

Aşağıdaki tabloda `DEVMODE` ve `TEXTMETRIC` dize dönüşüm makroları.

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>Ayrıca bkz.

[Makroları](../../atl/reference/atl-macros.md)
