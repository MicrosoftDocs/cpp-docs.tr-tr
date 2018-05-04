---
title: Dönüşüm makroları dize | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 917afc7dae7a0ed96d5d5cc476b4f8394abe8913
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="string-conversion-macros"></a>Dize dönüştürme makroları

Bu makroları dize dönüştürme özellikleri sağlar.  
 
##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL ve MFC dize dönüşüm makroları

Burada tartışılan dize dönüşüm makroları ATL ve MFC için geçerlidir. MFC dize dönüştürme hakkında daha fazla bilgi için bkz: [TN059: MFC MBCS/Unicode dönüştürme makrolarını kullanma](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) ve [MFC makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md).

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  Aygıt MODUNDAN ve TEXTMETRIC dize dönüşüm makroları

Bu makroları bir kopyasını oluşturacak bir [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) veya [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) yapısı ve yeni yapısı içinde dizeleri yeni bir dize türüne dönüştürün. Makrolar yeni yapısı için bellek yığında ve yeni yapısına bir işaretçi döndürür.  
  
```cpp
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>Açıklamalar

Örneğin:  
  
[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
ve:  
  
[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
Makro adlarında string kaynak yapısındaki sol tarafta türüdür (örneğin, **A**) ve hedef yapısındaki dize türü sağ tarafta (örneğin, **W**). **A** anlamına gelir `LPSTR`, **OLE** anlamına gelir `LPOLESTR`, **T** anlamına gelir `LPTSTR`, ve **W** anlamına gelir `LPWSTR`.  
  
Bu nedenle, **DEVMODEA2W** kopya bir `DEVMODE` yapısı `LPSTR` içine dizeleri bir `DEVMODE` yapısı `LPWSTR` dizeleri **TEXTMETRICOLE2T** bir kopyalar`TEXTMETRIC`yapısı `LPOLESTR` içine dizeleri bir `TEXTMETRIC` yapısı `LPTSTR` dizeler ve benzeri.  
  
İçinde dönüştürülmüş iki dizeyi `DEVMODE` yapısı olan aygıt adı (`dmDeviceName`) ve form adı (`dmFormName`). `DEVMODE` Dize dönüşüm makroları da güncelleştirilmesi yapı boyutu (`dmSize`).  
  
İçinde dönüştürülmüş dört dizeleri `TEXTMETRIC` yapısı olan ilk karakter (`tmFirstChar`), son karakter (`tmLastChar`), varsayılan karakter (`tmDefaultChar`) ve sonu karakteri (`tmBreakChar`).
  
Davranışını `DEVMODE` ve `TEXTMETRIC` dize dönüşüm makroları bağımlı geçerlilik derleyici yönergesinde varsa. Kaynak ve hedef türleri aynıysa dönüştürme gerçekleşir. Derleyici yönergeleri değiştirme **T** ve **OLE** gibi:  
  
|Efekti derleyici yönergesi|T olur|OLE olur|  
|----------------------------------|---------------|-----------------|  
|yok|**A**|**W**|  
|**\_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**\_UNICODE** ve **OLE2ANSI**|**W**|**A**|  
  
 Aşağıdaki tabloda `DEVMODE` ve `TEXTMETRIC` dönüşüm makroları dize.  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
