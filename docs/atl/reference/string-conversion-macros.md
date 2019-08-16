---
title: Dize dönüştürme makroları
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
ms.openlocfilehash: f7d9548fc5710e8d3d5d668dff230a60e7a291a1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495187"
---
# <a name="string-conversion-macros"></a>Dize dönüştürme makroları

Bu makrolar dize dönüştürme özellikleri sağlar.

##  <a name="atl_and_mfc_string_conversion_macros"></a>ATL ve MFC dize dönüştürme makroları

Burada ele alınan dize dönüştürme makroları hem ATL hem de MFC için geçerlidir. MFC dize dönüştürmesi hakkında daha fazla bilgi için bkz [. TN059: MFC MBCS/Unicode dönüştürme makrolarını](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) ve [MFC makrolarını ve Globals 'yi](../../mfc/reference/mfc-macros-and-globals.md)kullanma.

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE ve TEXTMETRIC dize dönüştürme makroları

Bu makrolar, [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veya [textmetric](/windows/win32/api/wingdi/ns-wingdi-textmetricw) yapısının bir kopyasını oluşturur ve yeni yapıdaki dizeleri yeni bir dize türüne dönüştürür. Makrolar yeni yapı için yığında bellek ayırır ve yeni yapıya bir işaretçi döndürür.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Açıklamalar

Örneğin:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

ve:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

Makro adlarında, kaynak yapıdaki dize türü solda (örneğin, **bir**) ve hedef yapıdaki dize türü sağda (örneğin, **W**). , LPStr 'yi temsil eder, **OLE** lpopastr 'Yi temsil eder, **T** , LPTSTR için ve **W** , LPWStr için temsil eder.

Bu nedenle DEVMODEA2W, bir `DEVMODE` yapıyı `DEVMODE` LPWStr dizeleri olan bir yapıya kopyalar, TEXTMETRICOLE2T lpopastr dizelerine `TEXTMETRIC` sahip bir yapıyı LPTSTR dizeleri olan bir `TEXTMETRIC` yapıya kopyalar ve bu şekilde devam eder.

`DEVMODE` Yapıda dönüştürülen iki dize cihaz adı (`dmDeviceName`) ve form adı (`dmFormName`). Dize dönüştürme makroları Ayrıca yapı boyutunu (`dmSize`) güncelleştirir. `DEVMODE`

`TEXTMETRIC` Yapıda dönüştürülen dört dize ilk karakterdir (`tmFirstChar`), son karakter (`tmLastChar`), varsayılan karakter (`tmDefaultChar`) ve kesme karakteri (`tmBreakChar`).

`DEVMODE` Ve`TEXTMETRIC` dize dönüştürme makrolarının davranışı, varsa derleyici yönergesinin etkin olduğunu gösterir. Kaynak ve hedef türleri aynıysa, herhangi bir dönüştürme gerçekleşmez. Derleyici yönergeleri **T** ve **OLE** 'yi aşağıdaki şekilde değiştirir:

|Derleyici yönergesi etkin|T olur|OLE şu şekilde olur|
|----------------------------------|---------------|-----------------|
|yok|**A**|**W**|
|**\_KODLAMALARI**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|UNICODE ve **OLE2ANSI**  **\_**|**W**|**A**|

Aşağıdaki tabloda `DEVMODE` ve `TEXTMETRIC` dize dönüştürme makroları listelenmektedir.

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>Ayrıca bkz.

[Larının](../../atl/reference/atl-macros.md)
