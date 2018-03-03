---
title: "Standart iletişim kutusu veri doğrulama yordamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33566bcdfab1a618dc8ff79deb375b3f9d1221f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="standard-dialog-data-validation-routines"></a>Standart İletişim Kutusu Veri Doğrulama Rutinleri
Bu konu genel MFC iletişim kutusu denetimleri için kullanılan standart iletişim kutusu veri doğrulama (DDV) yordamları listeler.  
  
> [!NOTE]
>  Standart iletişim kutusu veri değişimi rutinleri üstbilgi dosyası afxdd_.h tanımlanır. Ancak, uygulamaları afxwin.h içermelidir.  
  
### <a name="ddv-functions"></a>DDV işlevleri  
  
|||  
|-|-|  
|[DDV_MaxChars](#ddv_maxchars)|Verilen denetim değerinin karakter sayısı belirli bir maksimum değeri aşmadığını denetler.|  
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Belirli bir denetim değeri aşamaz doğrular bir verilen **bayt** aralığı.|  
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Belirli bir denetim değer belirli bir zaman aralığı aşmayan doğrular.|  
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Belirli bir denetim değeri aşamaz doğrular bir verilen **çift** aralığı.|  
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Belirli bir denetim değeri aşamaz doğrular bir verilen **DWORD** aralığı.|  
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Belirli bir denetim değeri aşamaz doğrular bir verilen **float** aralığı.|  
|[Ddv_minmaxınt](#ddv_minmaxint)|Belirli bir denetim değeri aşamaz doğrular bir verilen **int** aralığı.|  
|[DDV_MinMaxLong](#ddv_minmaxlong)|Belirli bir denetim değeri aşamaz doğrular bir verilen **uzun** aralığı.|  
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Belirli bir denetim değeri aşamaz doğrular bir verilen **LONGLONG** aralık.|  
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Belirli bir denetim değeri belirtilen tarih aralığı aşmayan doğrular.|  
|[DDV_MinMaxShort](#ddv_minmaxshort)|Belirli bir denetim değeri aşamaz doğrular bir verilen **kısa** aralığı.|  
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Verilen kaydırıcı denetimi değer içinde verilen aralığının doğrular.|  
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Belirli bir denetim değeri aşamaz doğrular bir verilen **UINT** aralığı.|  
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Belirli bir denetim değeri belirtilen iki değerin arasındadır sınırları doğrular.| 
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Belirli bir denetim değeri aşamaz doğrular bir verilen **ULONGLONG** aralık.|  
  

  
##  <a name="ddv_maxchars"></a>DDV_MaxChars  
 Çağrı `DDV_MaxChars` denetim karakterleri miktarı ile ilişkili olduğunu doğrulamak için *değeri* aşmayan *nChars*.  
  
```   
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,  
    CString const& value,  
    int nChars); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `nChars`  
 İzin verilen karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxbyte"></a>DDV_MinMaxByte  
 Çağrı `DDV_MinMaxByte` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,  
    BYTE value,  
    BYTE minVal,  
    BYTE maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **bayt**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **bayt**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime  
 Çağrı `DDV_MinMaxDateTime` tarih ve Saat Seçici saat/tarih değeri denetim doğrulamak için ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) ile ilişkili *refValue* arasında kalan `refMinRange` ve `refMaxRange`.  
  
```   
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar. Bu nesneyi silmek gerek yoktur.  
  
 *refValue*  
 Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) iletişim kutusu, form görünümü veya denetim görünüm nesnesi üye değişkeni ile ilişkili nesne. Bu nesne doğrulanacak verileri içerir.  
  
 `refMinRange`  
 Minimum tarih izin verilen değer.  
  
 `refMaxRange`  
 İzin verilen en fazla tarih/saat değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble  
 Çağrı `DDV_MinMaxDouble` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,  
    double const& value,  
    double minVal,  
    double maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **çift**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **çift**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxdword"></a>DDV_MinMaxDWord  
 Çağrı `DDV_MinMaxDWord` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,  
    DWORD const& value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür `DWORD`) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür `DWORD`) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat  
 Çağrı `DDV_MinMaxFloat` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,  
    float value,  
    float minVal,  
    float maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **float**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **float**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxint"></a>Ddv_minmaxınt  
 Çağrı `DDV_MinMaxInt` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,  
    int value,  
    int minVal,  
    int maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür `int`) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür `int`) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxlong"></a>DDV_MinMaxLong  
 Çağrı `DDV_MinMaxLong` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,  
    long value,  
    long minVal,  
    long maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **uzun**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **uzun**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong  
 Çağrı `DDV_MinMaxLongLong` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,  
    LONGLONG value,  
    LONGLONG minVal,  
    LONGLONG maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **LONGLONG**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **LONGLONG**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth  
 Çağrı `DDV_MinMaxMonth` Ay takvim saat/tarih değeri denetim doğrulamak için ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) ile ilişkili *refValue* arasında kalan `refMinRange` ve `refMaxRange`.  
  
```   
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *refValue*  
 Bir başvuru türünde bir nesne `CTime` veya `COleDateTime` iletişim kutusunda bir üye değişkeni ile ilişkilendirilmiş, form görünümü veya denetim görünüm nesnesi. Bu nesne doğrulanacak verileri içerir. Bu başvuru ne zaman MFC geçişleri `DDV_MinMaxMonth` olarak adlandırılır.  
  
 `refMinRange`  
 Minimum tarih izin verilen değer.  
  
 `refMaxRange`  
 İzin verilen en fazla tarih/saat değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxshort"></a>DDV_MinMaxShort  
 Çağrı `DDV_MinMaxShort` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,  
    short value,  
    short minVal,  
    short maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **kısa**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **kısa**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxslider"></a>DDV_MinMaxSlider  
 Çağrı `DDV_MinMaxSlider` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,  
    DWORD value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 Doğrulanacak değeri referansı. Bu parametre tutan veya kaydırıcı denetimin geçerli kaydırma konumunu ayarlar.  
  
 `minVal`  
 İzin verilen minimum değer.  
  
 `maxVal`  
 İzin verilen maksimum değer.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz: [kullanarak CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxuint"></a>DDV_MinMaxUInt  
 Çağrı `DDV_MinMaxUInt` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,  
    UINT value,  
    UINT minVal,  
    UINT maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **UINT**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **UINT**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong  
 Çağrı `DDV_MinMaxULongLong` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,  
    ULONGLONG value,  
    ULONGLONG  minVal ,  
    ULONGLONG  maxVal); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **ULONGLONG**) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **ULONGLONG**) izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Standart iletişim kutusu veri değişimi rutinleri](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)

 ## <a name="ddvminmaxunsigned"></a>DDV_MinMaxUnsigned
Çağrı `DDV_MinMaxUnsigned` denetimi değeri ile ilişkili olduğunu doğrulamak için *değeri* arasında kalan `minVal` ve `maxVal`.  
   
### <a name="syntax"></a>Sözdizimi    
```
   void AFXAPI DDV_MinMaxUnsigned(  
       CDataExchange* pDX,  
       unsigned value,  
       unsigned minVal,  
       unsigned maxVal );  
```
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *value*  
 İletişim kutusu, form görünümü veya verinin doğrulandığı denetim görünüm nesnesi üye değişkeni bir başvuru.  
  
 `minVal`  
 En düşük değer (tür **imzasız** ) izin verilir.  
  
 `maxVal`  
 En büyük değeri (tür **imzasız** ) izin verilir.  
   
### <a name="remarks"></a>Açıklamalar  
 DDV hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../dialog-data-exchange-and-validation.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdd_.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [DDX_Slider](#ddx_slider)   
 [DDX_FieldSlider](#ddx_fieldslider)
 


