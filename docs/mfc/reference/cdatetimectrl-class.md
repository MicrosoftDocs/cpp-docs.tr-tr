---
title: "CDateTimeCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ced7bfbb2cedd8cad4353cdbb2d5627864de5ad7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl sınıfı
Bir tarih ve Saat Seçici denetimini işlevselliği kapsar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Oluşturan bir `CDateTimeCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Geçerli tarih ve Saat Seçici denetimini kapatır.|  
|[CDateTimeCtrl::Create](#create)|Tarih ve Saat Seçici denetimini oluşturur ve ona ekler `CDateTimeCtrl` nesnesi.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Geçerli tarih ve Saat Seçici denetimini ilgili bilgileri alır.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Geçerli tarih ve saati görüntülemek için gereken tarih ve Saat Seçici denetimini ideal boyutu döndürür.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Ay takvim tarih ve Saat Seçici denetimini içinde belirli bir kısmı için renk alır.|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|Alır `CMonthCalCtrl` tarih ve saat seçici denetimi ile ilişkilendirilmiş nesne.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Tarih ve Saat Seçici denetimin alt aylık takvim denetiminin tarafından şu anda kullanılan yazı tipini alır.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Geçerli tarih ve Saat Seçici denetimini stilini alır.|  
|[CDateTimeCtrl::GetRange](#getrange)|Minimum ve maksimum geçerli bir tarih ve Saat Seçici denetimini sistem saatleri izin alır.|  
|[CDateTimeCtrl::GetTime](#gettime)|Tarih ve Saat Seçici denetimden şu anda seçili zaman alır ve belirtilen yerleştirir `SYSTEMTIME` yapısı.|  
|[CDateTimeCtrl::SetFormat](#setformat)|Belirtilen biçim dizesi uygun bir tarih ve Saat Seçici denetim görüntüsünü ayarlar.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Ay takvim tarih ve Saat Seçici denetimini içinde belirli bir kısmı rengini belirler.|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|Tarih ve Saat Seçici denetimin alt aylık takvim denetiminin kullanacağı yazı tipini belirler.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Geçerli tarih ve Saat Seçici denetimini stilini ayarlar.|  
|[CDateTimeCtrl::SetRange](#setrange)|Minimum ve maksimum izin verilen sistem saatleri tarih ve saat seçici denetimi için ayarlar.|  
|[CDateTimeCtrl::SetTime](#settime)|Bir tarih ve Saat Seçici denetiminde süreyi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tarih ve Saat Seçici denetimini (DTP denetimi) bir kullanıcıyla tarih ve saat bilgilerini değiştirmek için basit bir arabirim sağlar. Bu arabirim her biri bir parçası denetiminde tutulan tarih ve saat bilgilerini görüntüleyen alanları içerir. Kullanıcının belirli bir alandaki dize içeriğini değiştirerek denetiminde depolanan bilgileri değiştirebilirsiniz. Kullanıcı, fare veya klavye alan alanını kullanarak taşıyabilirsiniz.  
  
 Tarih ve Saat Seçici denetimini oluşturduğunuz nesneye çeşitli stiller uygulayarak özelleştirebilirsiniz. Bkz: [tarih ve Saat Seçici denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb761728) tarih ve Saat Seçici denetimine özgü stiller hakkında daha fazla bilgi için Windows SDK'sındaki. Biçim stilleri kullanarak DTP denetimi görüntüleme biçimi ayarlayabilirsiniz. Bu biçim stiller Windows SDK konuda "Biçimi stiller" altında açıklanan [tarih ve Saat Seçici denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb761728).  
  
 Tarih ve Saat Seçici denetim bildirimleri ve açıklanan geri aramalar kullanan [kullanarak CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdtctl.h  
  
##  <a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 Oluşturan bir `CDateTimeCtrl` nesnesi.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 Geçerli tarih ve Saat Seçici denetimini kapatır.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_dateTimeCtrl`, yani tarih ve Saat Seçici denetimine programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde geçerli tarih ve Saat Seçici denetimini açılan Takvim kapatır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="create"></a>CDateTimeCtrl::Create  
 Tarih ve Saat Seçici denetimini oluşturur ve ona ekler `CDateTimeCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Tarih Saat Denetim stilleri bileşimini belirtir. Bkz: [tarih ve Saat Seçici denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb761728) tarih ve Saat Seçici stilleri hakkında daha fazla bilgi için Windows SDK'sındaki.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) konum ve boyutlarının tarih ve Saat Seçici denetimini yapısı.  
  
 `pParentWnd`  
 Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) tarih ve Saat Seçici denetimini üst pencere nesnesi. Değil olmalıdır **NULL**.  
  
 `nID`  
 Tarih ve Saat Seçici denetimin denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturma başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>Bir tarih ve Saat Seçici denetimini oluşturmak için  
  
1.  Çağrı [CDateTimeCtrl](#cdatetimectrl) oluşturmak için bir `CDateTimeCtrl` nesnesi.  
  
2.  Windows tarih ve Saat Seçici denetimini oluşturup ekleninceye bu üye işlevini çağırın `CDateTimeCtrl` nesnesi.  
  
 Çağırdığınızda **oluşturma**, ortak denetimleri başlatılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 Geçerli tarih ve Saat Seçici denetimini ilgili bilgileri alır.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out]`pDateTimePickerInfo`|Bir işaretçi bir [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729) yapısı geçerli tarih ve Saat Seçici denetimini açıklamasını alır.<br /><br /> Bu yapı ayırma için çağıran sorumludur. Ancak, bu yöntem başlatır `cbSize` yapısı üyesi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_dateTimeCtrl`, yani tarih ve Saat Seçici denetimine programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, geçerli tarih ve saat seçici denetimi hakkındaki bilgiler başarıyla alır olup olmadığını gösterir.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 Ay takvim tarih ve Saat Seçici denetimini içinde belirli bir kısmı için renk alır.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `iColor`  
 Bir `int` almak için ay Takvim rengi alanı belirten değer. Değerlerinin listesi için bkz: `iColor` parametresi için [SetMonthCalColor](#setmonthcalcolor).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **COLORREF** başarılı olursa aylık takvim denetiminin belirtilen bölümü için renk ayarı gösteren bir değer. İşlem başarısız olursa, işlevi -1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl  
 Alır `CMonthCalCtrl` tarih ve saat seçici denetimi ile ilişkilendirilmiş nesne.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) nesnesi veya **NULL** başarısız olursa veya pencere görünür değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı aşağı açılan okunu tıklattığında tarih ve Saat Seçici denetimleri alt aylık takvim denetiminin oluşturun. Zaman `CMonthCalCtrl` nesne artık gerekli, uygulamanızın tarih saat Seçici denetimin alt Ay takvim temsil eden nesne depolama kalmamanız gerekir böylece bu yok edilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 Tarih ve Saat Seçici denetimin aylık takvim denetiminin tarafından şu anda kullanılan yazı tipini alır.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CFont](../../mfc/reference/cfont-class.md) nesnesi veya **NULL** başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 `CFont` Dönüş değeri tarafından işaret nesnesi geçici bir nesne ve sonraki boşta kalma işleme süresinde yok.  
  
##  <a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 Geçerli tarih ve Saat Seçici denetimle ilişkili açılan aylık takvim denetiminin stilini alır.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarih ve Saat Seçici denetim stilleri (veya) Bitsel bir birleşimi aşağı açılan aylık takvim denetiminin stili. Daha fazla bilgi için bkz: [ay Takvim denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760919).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getrange"></a>CDateTimeCtrl::GetRange  
 Minimum ve maksimum geçerli bir tarih ve Saat Seçici denetimini sistem saatleri izin alır.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pMinRange`  
 Bir işaretçi bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi veya bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) izin verilen en erken zaman içeren bir nesne `CDateTimeCtrl` nesne.  
  
 `pMaxRange`  
 Bir işaretçi bir `COleDateTime` nesnesi veya bir `CTime` izin verilen en geç saati içeren bir nesne `CDateTimeCtrl` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `DWORD` hangi aralıkları ayarlama belirten bayrakları içeren değeri. Eğer  
  
 `return value & GDTR_MAX` == 0  
  
 ardından ikinci parametre geçerli değil. Benzer şekilde, varsa  
  
 `return value & GDTR_MIN` == 0  
  
 ardından ilk parametresi geçerli değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767), Windows SDK'ın açıklandığı gibi. MFC'nin uygulamasında ya da belirtebilirsiniz `COleDateTime` veya `CTime` kullanımları.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="gettime"></a>CDateTimeCtrl::GetTime  
 Tarih ve Saat Seçici denetimden şu anda seçili zaman alır ve belirtilen yerleştirir `SYSTEMTIME` yapısı.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *timeDest*  
 İlk sürümünde, bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) sistem zamanı bilgileri alacak nesnesi. İkinci sürümünde, bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) sistem zamanı bilgileri alacak nesnesi.  
  
 *pTimeDest*  
 Bir işaretçi [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) sistem zamanı bilgileri almak için yapısı. Olmamalıdır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürümünde, zaman başarıyla yazılır, sıfır olmayan `COleDateTime` nesnesi; Aksi takdirde 0. İkinci ve üçüncü sürümlerinde, bir `DWORD` değerine eşit bir değer **dwFlag** üye kümesinde [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) yapısı. Bkz: **açıklamalar** daha fazla bilgi için bölüm aşağıda.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769), Windows SDK'ın açıklandığı gibi. MFC uygulamasında **GetTime**, kullanabileceğiniz `COleDateTime` veya `CTime` sınıfları veya kullanabilirsiniz bir `SYSTEMTIME` zaman bilgilerini depolamak için yapısı.  
  
 Dönüş değeri `DWORD` ikinci ve üçüncü sürümlerde, yukarıdaki tarih ve Saat Seçici denetimini "tarih" durumuna ayarlanmış olup olmadığını de belirtildiği gibi gösterir [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) yapısı üye `dwFlags`. Değer eşittir döndürülürse **GDT_NONE**, denetimi "tarih" durumuna ayarlanır ve kullandığı **DTS_SHOWNONE** stili. Değer eşittir döndürülürse **GDT_VALID**, sistem saatini başarıyla hedef konumda depolanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 Geçerli tarih ve saati görüntülemek için gereken tarih ve Saat Seçici denetimini ideal boyutu döndürür.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out]`psize`|İşaretçi bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) denetimi için ideal boyutu içeren yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri her zaman olduğu `true`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_dateTimeCtrl`, yani tarih ve Saat Seçici denetimine programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği tarih ve Saat Seçici denetimini görüntülemek için ideal boyutu alır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="setformat"></a>CDateTimeCtrl::SetFormat  
 Belirtilen biçim dizesi uygun bir tarih ve Saat Seçici denetim görüntüsünü ayarlar.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>Parametreler  
 *pstrFormat*  
 İstediğiniz görüntüleme tanımlayan sıfır sonlandırılan biçim dizesi için bir işaretçi. Bu parametre ayarını **NULL** denetimi geçerli stil için varsayılan biçim dizesini sıfırlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
> [!NOTE]
>  Kullanıcı girişi bu çağrı için başarı veya başarısızlık belirlemez.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 Ay takvim tarih ve Saat Seçici denetimini içinde belirli bir kısmı rengini belirler.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Parametreler  
 `iColor`  
 `int`Aylık takvim denetiminin ayarlanacak alanı belirten değer. Bu değer aşağıdakilerden biri olabilir.  
  
|Değer|Açıklama|  
|-----------|-------------|  
|MCSC_BACKGROUND|Ay arasında görüntülenen arka plan rengini ayarlayın.|  
|MCSC_MONTHBK|Bir ay içinde görüntülenen arka plan rengini ayarlayın.|  
|MCSC_TEXT|Metin bir ay içinde görüntülemek için kullanılan rengi ayarlayın.|  
|MCSC_TITLEBK|Takvim başlığında görüntülenen arka plan rengini ayarlayın.|  
|MCSC_TITLETEXT|Takvim başlık içindeki metnin görüntülemek için kullanılan rengi ayarlayın.|  
|MCSC_TRAILINGTEXT|Üstbilgi ve sondaki gün metnini görüntülemek için kullanılan rengi ayarlayın. Üstbilgi ve sondaki gün geçerli takvimde görünen önceki ve sonraki aylarda günlük olur.|  
  
 `ref`  
 A **COLORREF** ay Takvim belirtilen alan için ayarlanacak rengi temsil eden değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **COLORREF** başarılı olursa aylık takvim denetiminin belirtilen bölümü için önceki renk ayarı gösteren bir değer. Aksi takdirde, message -1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).  
  
##  <a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont  
 Tarih ve Saat Seçici denetimin alt aylık takvim denetiminin kullanacağı yazı tipini belirler.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `hFont`  
 Ayarlanacak yazı tipi işleyin.  
  
 `bRedraw`  
 Denetim hemen yazı tipini ayarlama üzerine gizlenmesinin olup olmadığını belirtir. Bu parametre ayarını **TRUE** kendisini yeniden çizmek denetimi neden olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  Bu kod kullanırsanız, üyesi olmak istersiniz, `CDialog`-türetilmiş sınıf adlı `m_MonthFont` türü **CFont**.  
  
##  <a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 Geçerli tarih ve Saat Seçici denetimle ilişkili açılan aylık takvim denetiminin stilini ayarlar.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`dwStyle`|Ay takvim denetimi stilleri Bitsel bir birleşimi (veya) olan yeni ay Takvim denetimi stili. Daha fazla bilgi için bkz: [ay Takvim denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760919).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağı açılan aylık takvim denetiminin önceki stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_dateTimeCtrl`, yani tarih ve Saat Seçici denetimine programlı olarak erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde hafta sayıları, haftanın günü ve bugün gösterge gün kısaltılmış adlarını görüntülemek için tarih ve Saat Seçici denetimini ayarlar.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CDateTimeCtrl::SetRange  
 Minimum ve maksimum izin verilen sistem saatleri tarih ve saat seçici denetimi için ayarlar.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMinRange`  
 Bir işaretçi bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi veya bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) izin verilen en erken zaman içeren bir nesne `CDateTimeCtrl` nesne.  
  
 `pMaxRange`  
 Bir işaretçi bir `COleDateTime` nesnesi veya bir `CTime` izin verilen en geç saati içeren bir nesne `CDateTimeCtrl` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780), Windows SDK'ın açıklandığı gibi. MFC'nin uygulamasında ya da belirtebilirsiniz `COleDateTime` veya `CTime` kullanımları. Varsa `COleDateTime` nesnesi bir **NULL** durumu, aralığın kaldırılacak. Varsa `CTime` işaretçi veya `COleDateTime` işaretçi **NULL**, aralığın kaldırılacak.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CDateTimeCtrl::GetRange](#getrange).  
  
##  <a name="settime"></a>CDateTimeCtrl::SetTime  
 Bir tarih ve Saat Seçici denetiminde süreyi ayarlar.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *timeNew*  
 Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesini içeren denetimi ayarlanacak için.  
  
 *pTimeNew*  
 İkinci sürümünde yukarıdaki gösteren bir işaretçi bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) olduğu denetimi ayarlanacak saati içeren bir nesne. Yukarıdaki gösteren bir işaretçi üçüncü sürümündeki bir [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) olduğu denetimi ayarlanacak saati içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782), Windows SDK'ın açıklandığı gibi. MFC uygulamasında **SetTime**, kullanabileceğiniz `COleDateTime` veya `CTime` sınıfları veya kullanabilirsiniz bir `SYSTEMTIME` saat bilgisi ayarlamak için yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl sınıfı](../../mfc/reference/cmonthcalctrl-class.md)
