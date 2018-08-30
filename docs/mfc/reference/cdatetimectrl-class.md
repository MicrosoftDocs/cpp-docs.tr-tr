---
title: CDateTimeCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
dev_langs:
- C++
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdf2134b334c259a6543af279ee058b659cf21d6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210193"
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl sınıfı
Bir tarih ve Saat Seçici denetiminin işlevselliğini kapsüller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Oluşturur bir `CDateTimeCtrl` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Geçerli tarih ve Saat Seçici denetimini kapatır.|  
|[CDateTimeCtrl::Create](#create)|Tarih ve saat seçici denetimi oluşturur ve ona ekler `CDateTimeCtrl` nesne.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Geçerli tarih ve saat seçici denetimi ile ilgili bilgileri alır.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|İdeal boyutu geçerli tarih ve saati görüntülemek için gerekli olan tarih ve saat seçici denetimi değerini döndürür.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Ay takvim tarih ve Saat Seçici denetiminde belirli bir kısmı için renk alır.|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|Alır `CMonthCalCtrl` tarih ve Saat Seçici denetiminin ilişkili nesne.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Tarih ve Saat Seçici denetiminin alt ay takvimi tarafından şu anda kullanılan yazı tipini alır.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Geçerli tarih ve Saat Seçici denetiminin stilini alır.|  
|[CDateTimeCtrl::GetRange](#getrange)|Sistem saatleri bir tarih ve saat seçici denetimi için izin verilen minimum ve maksimum geçerli alır.|  
|[CDateTimeCtrl::GetTime](#gettime)|Bir tarih ve saat seçici denetimi seçili zaman alır ve belirtilen koyar `SYSTEMTIME` yapısı.|  
|[CDateTimeCtrl::SetFormat](#setformat)|Görüntü verilen biçim dizesi uygun olarak bir tarih ve saat seçici denetimi değerini ayarlar.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Ay takvim içinden bir tarih ve Saat Seçici denetimini belirli bir kısmı rengini belirler.|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|Tarih ve Saat Seçici denetiminin alt aylık takvim denetiminin kullanacağı yazı tipini ayarlar.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Geçerli tarih ve Saat Seçici denetiminin stilini ayarlar.|  
|[CDateTimeCtrl::SetRange](#setrange)|Bir tarih ve saat seçici denetimi için minimum ve maksimum izin verilen sistem saatleri ayarlar.|  
|[CDateTimeCtrl::SetTime](#settime)|Bir tarih ve Saat Seçici denetiminde süreyi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tarih ve Saat Seçici denetimini (DTP denetiminde) bir tarih ve saat bilgilerini değiştirmek için basit bir arabirim sağlar. Bu arabirim, her biri bir bölümü denetiminde depolanmış tarih ve saat bilgilerini görüntüler. alanları içerir. Kullanıcı denetimi dizesini verilen bir alanda içeriğini değiştirerek depolanan bilgileri değiştirebilirsiniz. Kullanıcı, klavye veya fare alan alanını kullanarak taşıyabilirsiniz.  
  
 Oluşturduğunuz nesneye çeşitli stilleri uygulayarak, tarih ve Saat Seçici denetimini özelleştirebilirsiniz. Bkz: [tarih ve Saat Seçici denetim stilleri](/windows/desktop/Controls/date-and-time-picker-control-styles) tarih ve Saat Seçici denetimine belirli stilleri hakkında daha fazla bilgi için Windows SDK. Biçim stilleri kullanarak DTP denetiminde görüntüleme biçimini ayarlayabilirsiniz. Bu biçim stilleri Windows SDK'sı konuda "Biçim stiller" altında açıklanan [tarih ve Saat Seçici denetim stilleri](/windows/desktop/Controls/date-and-time-picker-control-styles).  
  
 Tarih ve Saat Seçici denetimini bildirimleri ve şurada açıklanan geri çağırmaları kullanan [kullanarak CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdtctl.h  
  
##  <a name="cdatetimectrl"></a>  CDateTimeCtrl::CDateTimeCtrl  
 Oluşturur bir `CDateTimeCtrl` nesne.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="closemonthcal"></a>  CDateTimeCtrl::CloseMonthCal  
 Geçerli tarih ve Saat Seçici denetimini kapatır.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_CLOSEMONTHCAL](/windows/desktop/Controls/dtm-closemonthcal) Windows SDK'da açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği değişkeni tanımlar *m_dateTimeCtrl*diğer bir deyişle, tarih ve Saat Seçici denetimini programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, geçerli tarih ve saat seçici denetimi için açılan takvimin kapatır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="create"></a>  CDateTimeCtrl::Create  
 Tarih ve saat seçici denetimi oluşturur ve ona ekler `CDateTimeCtrl` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 Tarih Saat Denetim stilleri bileşimini belirtir. Bkz: [tarih ve Saat Seçici denetim stilleri](/windows/desktop/Controls/date-and-time-picker-control-styles) tarih ve Saat Seçici stilleri hakkında daha fazla bilgi için Windows SDK.  
  
 *Rect*  
 Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) tarih ve Saat Seçici denetiminin boyutunu ve konumunu olan yapısı.  
  
 *pParentWnd*  
 Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) tarih ve Saat Seçici denetiminin üst penceresine olan nesne. NULL olmamalıdır.  
  
 *nID*  
 Tarih ve Saat Seçici denetiminin denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturma başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>Bir tarih ve Saat Seçici denetimini oluşturma  
  
1.  Çağrı [CDateTimeCtrl](#cdatetimectrl) oluşturmak için bir `CDateTimeCtrl` nesne.  
  
2.  Windows tarih ve Saat Seçici denetimini oluşturan ve ekler bu üye işlevi çağrısı `CDateTimeCtrl` nesne.  
  
 Çağırdığınızda `Create`, ortak denetimleri yeniden başlatılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="getdatetimepickerinfo"></a>  CDateTimeCtrl::GetDateTimePickerInfo  
 Geçerli tarih ve saat seçici denetimi ile ilgili bilgileri alır.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out] *pDateTimePickerInfo*|Bir işaretçi bir [DATETIMEPICKERINFO](/windows/desktop/api/commctrl/ns-commctrl-tagdatetimepickerinfo) yapısı geçerli tarih ve Saat Seçici denetiminin açıklamasını alır.<br /><br /> Bu yapı ayırma için çağıran sorumludur. Ancak, bu yöntem başlatır *cbSize* yapı üyesi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_GETDATETIMEPICKERINFO](/windows/desktop/Controls/dtm-getdatetimepickerinfo) Windows SDK'da açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği değişkeni tanımlar *m_dateTimeCtrl*diğer bir deyişle, tarih ve Saat Seçici denetimini programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, geçerli tarih ve saat seçici denetimi ile ilgili bilgileri başarıyla alır olup olmadığını gösterir.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="getmonthcalcolor"></a>  CDateTimeCtrl::GetMonthCalColor  
 Ay takvim tarih ve Saat Seçici denetiminde belirli bir kısmı için renk alır.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *iColor*  
 Bir **int** almak için aylık takvim renk alanı belirten değer. Değerler listesi için bkz. *iColor* parametresi için [SetMonthCalColor](#setmonthcalcolor).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ay takvim denetimi başarılı olursa belirtilen kısmı için renk ayarları temsil eden bir COLORREF değeri. İşlem başarısız olursa, işlev -1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_GETMCCOLOR](/windows/desktop/Controls/dtm-getmccolor)Windows SDK içinde açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="getmonthcalctrl"></a>  CDateTimeCtrl::GetMonthCalCtrl  
 Alır `CMonthCalCtrl` tarih ve Saat Seçici denetiminin ilişkili nesne.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) nesne veya başarısız olursa veya pencerede görünür değilse NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı aşağı açılan okunu tıkladığında bir alt aylık takvim denetiminin tarih ve Saat Seçici denetimleri oluşturun. Zaman `CMonthCalCtrl` nesne artık gerekli, böylece uygulamanız tarih saat Seçici denetiminin alt ay takvimi temsil eden bir nesneyi depolamak üzerinde durumda değil, yok edilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="getmonthcalfont"></a>  CDateTimeCtrl::GetMonthCalFont  
 Tarih ve Saat Seçici denetiminin ay takvimi tarafından şu anda kullanılan yazı tipini alır.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CFont](../../mfc/reference/cfont-class.md) nesne veya başarısız olursa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 `CFont` Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve sonraki boşta işleme sırada yok edilir.  
  
##  <a name="getmonthcalstyle"></a>  CDateTimeCtrl::GetMonthCalStyle  
 Geçerli tarih ve saat seçici denetimi ile ilişkili açılan aylık takvim denetiminin stilini alır.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarih ve Saat Seçici denetim stilleri (veya) karşılaştırmaya aşağı açılan aylık takvim denetiminin stili. Daha fazla bilgi için [aylık takvim denetimi stilleri](/windows/desktop/Controls/month-calendar-control-styles).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_GETMCSTYLE](/windows/desktop/Controls/dtm-getmcstyle) Windows SDK'da açıklanan ileti.  
  
##  <a name="getrange"></a>  CDateTimeCtrl::GetRange  
 Sistem saatleri bir tarih ve saat seçici denetimi için izin verilen minimum ve maksimum geçerli alır.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pMinRange*  
 Bir işaretçi bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi veya bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) izin verilen en erken zamanı içeren bir nesne `CDateTimeCtrl` nesne.  
  
 *pMaxRange*  
 Bir işaretçi bir `COleDateTime` nesnesi veya bir `CTime` içinde izin verilen en son süreyi içeren nesne `CDateTimeCtrl` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hangi aralıkları ayarlama belirten bayrakları içeren bir DWORD değeri. Eğer  
  
 `return value & GDTR_MAX` == 0  
  
 ardından ikinci parametresi geçerli değil. Benzer şekilde, varsa  
  
 `return value & GDTR_MIN` == 0  
  
 ardından ilk parametresi geçerli değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_GETRANGE](/windows/desktop/Controls/dtm-getrange)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında belirtebilirsiniz `COleDateTime` veya `CTime` kullanımları.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="gettime"></a>  CDateTimeCtrl::GetTime  
 Bir tarih ve saat seçici denetimi seçili zaman alır ve belirtilen koyar `SYSTEMTIME` yapısı.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *timeDest*  
 İlk sürümünde, bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) sistem saat bilgilerini alacak nesne. Dosyanın ikinci sürümü, bir başvuru olarak bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) sistem saat bilgilerini alacak nesne.  
  
 *pTimeDest*  
 Bir işaretçi [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) sistem saat bilgilerini almak için yapısı. NULL olmamalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürümünde, zaman başarıyla yazılır, sıfır olmayan `COleDateTime` nesne; Aksi durumda 0. İkinci ve üçüncü sürümlerinde, bir DWORD değeri eşittir *dwFlag* üye kümesinde [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) yapısı. Bkz: **açıklamalar** bölümünde daha fazla bilgi için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_GETSYSTEMTIME](/windows/desktop/Controls/dtm-getsystemtime)Windows SDK içinde açıklandığı gibi. MFC uygulamasında `GetTime`, kullanabilirsiniz `COleDateTime` veya `CTime` sınıfları veya kullanabileceğiniz bir `SYSTEMTIME` yapısı, saat bilgilerini depolamak için.  
  
 Dönüş değeri DWORD ikinci ve üçüncü sürümlerinde, yukarıdaki tarih ve Saat Seçici denetimini "tarih" durumuna ayarlanmış olup olmadığını, gösterildiği gibi gösterir [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) yapı üyesinin *CertOpenStore* . Döndürülen değer GDT_NONE eşitse, denetimi "tarih" durumuna ayarlanır ve DTS_SHOWNONE stili kullanır. Döndürülen değer GDT_VALID eşitse, sistem saati başarıyla hedef konumda depolanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="getidealsize"></a>  CDateTimeCtrl::GetIdealSize  
 İdeal boyutu geçerli tarih ve saati görüntülemek için gerekli olan tarih ve saat seçici denetimi değerini döndürür.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out] *psize*|İşaretçi bir [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) denetimi için ideal boyutu içeren yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri her zaman doğrudur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_GETIDEALSIZE](/windows/desktop/Controls/dtm-getidealsize) Windows SDK'da açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği değişkeni tanımlar *m_dateTimeCtrl*diğer bir deyişle, tarih ve Saat Seçici denetimini programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği tarih ve Saat Seçici denetimini görüntülemek için ideal boyutu alır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="setformat"></a>  CDateTimeCtrl::SetFormat  
 Görüntü verilen biçim dizesi uygun olarak bir tarih ve saat seçici denetimi değerini ayarlar.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>Parametreler  
 *pstrFormat*  
 İstediğiniz görüntüyü tanımlayan biçimi Sıfırla sonlandırılmış dizeye bir işaretçi. Bu parametre NULL olarak ayarlamak denetimi geçerli stili için varsayılan biçim dizesini sıfırlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
> [!NOTE]
>  Kullanıcı girişi, bu çağrı için başarı veya başarısızlık belirlemez.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_SETFORMAT](/windows/desktop/Controls/dtm-setformat)Windows SDK içinde açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="setmonthcalcolor"></a>  CDateTimeCtrl::SetMonthCalColor  
 Ay takvim içinden bir tarih ve Saat Seçici denetimini belirli bir kısmı rengini belirler.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Parametreler  
 *iColor*  
 **int** ayarlamak için aylık takvim denetiminin alanı belirten değer. Bu değer aşağıdakilerden biri olabilir.  
  
|Değer|Açıklama|  
|-----------|-------------|  
|MCSC_BACKGROUND|Arasındaki ay görüntülenen arka plan rengini ayarlayın.|  
|MCSC_MONTHBK|Bir ay içinde görüntülenen arka plan rengini ayarlayın.|  
|MCSC_TEXT|Bir ay içinde metin görüntülemek için kullanılan rengi ayarlayın.|  
|MCSC_TITLEBK|Takvimin başlığı görüntülenen arka plan rengini ayarlayın.|  
|MCSC_TITLETEXT|Takvimin başlığı içindeki metni görüntülemek için kullanılan rengi ayarlayın.|  
|MCSC_TRAILINGTEXT|Üst bilgi ve sondaki günlük metni görüntülemek için kullanılan rengi ayarlayın. Üst bilgi ve sondaki gün geçerli Takvim üzerinde görünen önceki ve sonraki aya ait günler geride kaldı.|  
  
 *ref*  
 Ay takvim belirtilen alan için ayarlanacak rengi temsil eden bir COLORREF değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ay takvim denetimi başarılı olursa belirtilen kısmı için önceki renk ayarları temsil eden bir COLORREF değeri. Aksi takdirde, iletinin -1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_SETMCCOLOR](/windows/desktop/Controls/dtm-setmccolor)Windows SDK içinde açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).  
  
##  <a name="setmonthcalfont"></a>  CDateTimeCtrl::SetMonthCalFont  
 Tarih ve Saat Seçici denetiminin alt aylık takvim denetiminin kullanacağı yazı tipini ayarlar.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *hFont*  
 Ayarlanacak yazı tipinin işleyin.  
  
 *bRedraw*  
 Denetim hemen yazı ayarını üzerine yeniden çizilmesi olup olmadığını belirtir. Bu parametre TRUE olarak ayarlandığında denetimin çizilmeyi neden olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_SETMCFONT](/windows/desktop/Controls/dtm-setmcfont)Windows SDK içinde açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  Bu kodu kullanırsanız, üyesi yapmak istersiniz, `CDialog`-türetilmiş sınıf adlı *m_MonthFont* türü `CFont`.  
  
##  <a name="setmonthcalstyle"></a>  CDateTimeCtrl::SetMonthCalStyle  
 Geçerli tarih ve saat seçici denetimi ile ilişkili açılan aylık takvim denetiminin stilini ayarlar.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *dwStyle*|Ay takvim denetimi stilleri bit düzeyinde birleşimi (veya) olan yeni aylık takvim denetimi stili. Daha fazla bilgi için [aylık takvim denetimi stilleri](/windows/desktop/Controls/month-calendar-control-styles).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan ay Takvim denetimi önceki stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_SETMCSTYLE](/windows/desktop/Controls/dtm-setmcstyle) Windows SDK'da açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği değişkeni tanımlar *m_dateTimeCtrl*diğer bir deyişle, tarih ve Saat Seçici denetimini programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, hafta sayıları, kısaltılmış gün haftanın günü ve bugün gösterge görüntülemek için tarih ve Saat Seçici denetimini ayarlar.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="setrange"></a>  CDateTimeCtrl::SetRange  
 Bir tarih ve saat seçici denetimi için minimum ve maksimum izin verilen sistem saatleri ayarlar.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>Parametreler  
 *pMinRange*  
 Bir işaretçi bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi veya bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) izin verilen en erken zamanı içeren bir nesne `CDateTimeCtrl` nesne.  
  
 *pMaxRange*  
 Bir işaretçi bir `COleDateTime` nesnesi veya bir `CTime` içinde izin verilen en son süreyi içeren nesne `CDateTimeCtrl` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_SETRANGE](/windows/desktop/Controls/dtm-setrange)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında belirtebilirsiniz `COleDateTime` veya `CTime` kullanımları. Varsa `COleDateTime` nesnesi NULL durumuna sahiptir, aralığın kaldırılacak. Varsa `CTime` işaretçi veya `COleDateTime` NULL bir işaretçiyse, aralığın kaldırılacak.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CDateTimeCtrl::GetRange](#getrange).  
  
##  <a name="settime"></a>  CDateTimeCtrl::SetTime  
 Bir tarih ve Saat Seçici denetiminde süreyi ayarlar.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *timeNew*  
 Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesini içeren için Denetim ayarlanır.  
  
 *pTimeNew*  
 İkinci Sürüm yukarıda, işaretçi bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) olduğu denetim ayarlanacak saati içeren bir nesne. Bir işaretçi yukarıdaki üçüncü sürümünde bir [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) için Denetim ayarlanacak zaman içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [DTM_SETSYSTEMTIME](/windows/desktop/Controls/dtm-setsystemtime)Windows SDK içinde açıklandığı gibi. MFC uygulamasında `SetTime`, kullanabilirsiniz `COleDateTime` veya `CTime` sınıfları veya kullanabileceğiniz bir `SYSTEMTIME` saat bilgisi ayarlamak için yapı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl Sınıfı](../../mfc/reference/cmonthcalctrl-class.md)
