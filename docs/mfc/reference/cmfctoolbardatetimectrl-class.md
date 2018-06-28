---
title: CMFCToolBarDateTimeCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31bf2796d85dec335183b61a83ea5c675d5f4602
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038952"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl sınıfı
Bir tarih ve Saat Seçici denetimini içeren bir araç çubuğu düğmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Oluşturan bir `CMFCToolBarDateTimeCtrl` nesnesi.|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Bir kullanıcı özelleştirmesi sırasında düğmesi uzatma olup olmadığını belirtir. (Geçersiz kılmaları [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi özelliklerini geçerli düğme kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Daha sonraki kullanımlar için ayrılmıştır.|  
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Metni araç çubuğu düğmesinden menü kopyalar.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|İlk alır `CMFCToolBarDateTimeCtrl` belirtilen komut kimliği olan uygulama nesnesinde|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Bir işaretçi tarih ve Saat Seçici denetimine döndürür.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Araç çubuğu düğmesi ile ilişkili bir pencere tanıtıcının alır. (Geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Tarih ve Saat Seçici denetimden seçilen zaman alır ve belirtilen yerleştirir [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) yapısı.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Seçilen zaman saat Seçici denetimini düğmesinden belirtilen komut kimliğe sahip döndürür|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Bir kullanıcı düğmesini seçtiğinde düğmesinin kenarlık görüntülenip görüntülenmeyeceğini belirler. (Geçersiz kılmaları [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Düğme işler olup olmadığını belirtir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) ileti. (Geçersiz kılmaları [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Düğme eklendiğinde çerçevesi tarafından çağrılır bir **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Takma durumunu ve belirtilen cihaz bağlamı düğmesini boyutunu hesaplamak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Yeni bir araç çubuğu düğmesi takıldığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Kullanıcı denetimi tıklattığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Üst araç WM_CTLCOLOR iletisi işlediğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|Belirtilen stilleri ve seçenekleri kullanarak düğmesi çizmek için framework tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Düğme çizmek için framework tarafından çağrılan **komutları** bölmesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Genel yazı tipi değiştiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Üst araç taşındığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Düğme olduğunda görünür veya görünmez çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|Üst araç boyutuna değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek için düğmesini çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Üst araç çubuğu araç ipucu metni güncelleştirdiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|Bu nesne arşivden okur veya bir arşiv için yazar (geçersiz kılmaları [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|Araç çubuğu düğmesi stilini ayarlar. (Geçersiz kılmaları [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Tarih ve Saat Seçici denetiminde ayarlar.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Tarih ve saat belirtilen komut kimliği olan tüm örneklerine Saat Seçici denetimini ayarlar|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tarih ve Saat Seçici denetimini nasıl kullanılacağını örneğin ToolbarDateTimePicker örnek proje bakın. Araç çubukları denetimi düğmeleri ekleme hakkında daha fazla bilgi için bkz: [izlenecek yol: üzerinde denetimler koyma araç'çubukları](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbardatetimectrl.h  
  
##  <a name="canbestretched"></a>  CMFCToolBarDateTimeCtrl::CanBeStretched  
 Bir kullanıcı özelleştirmesi sırasında düğmesi uzatma olup olmadığını belirtir.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bir araç çubuğu düğmesini özelleştirme sırasında uzatmak kullanıcı framework izin vermiyor. Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) bir tarih ve saat araç çubuğu düğmesini özelleştirme sırasında uzatmak kullanıcı sağlayarak.  
  
##  <a name="cmfctoolbardatetimectrl"></a>  CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl  
 Oluşturur ve başlatır bir [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) nesnesi.  
  
```  
CMFCToolBarDateTimeCtrl(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=0,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiID*  
 Denetim kimliği.  
  
 [in] *iImage*  
 Araç çubuğunun görüntüde dizinini `CMFCToolBarImages` nesnesi.  
  
 [in] *dwStyle*  
 Stilini `CMFCToolBarDateTimeCtrlImpl` kullanıcı düğmesine tıkladığında oluşturduğunuz penceresi.  
  
 [in] *iWidth*  
 Denetimin piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu nesne, sistem tarihi ve saati başlatılır. Pencere stili iç `CMFCToolBarDateTimeCtrlImpl` nesnesi içerir *dwStyle* parametre ve `WS_CHILD` ve `WS_VISIBLE` stilleri. Kullanarak bu stiller değiştiremezsiniz `CMFCToolBarDateTimeCtrl::SetStyle`. Kullanım `SetStyle` stilini değiştirmek için `CMFCToolBarDateTimeCtrl` denetim.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCToolBarDateTimeCtrl` sınıfı. Bu kod parçacığını parçası olan [araç tarih saat Seçici örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCToolBarDateTimeCtrl::CopyFrom  
 Başka bir araç çubuğu düğmesi özelliklerini geçerli düğme kopyalar.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *src*  
 Kaynak düğmesini başvuru kopyalanacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu araç çubuğu düğmesi için başka bir araç çubuğu düğmesini kopyalamak için bu yöntemi çağırın. *src* türünde olmalıdır `CMFCToolBarDateTimeCtrl`.  
  
##  <a name="exporttomenubutton"></a>  CMFCToolBarDateTimeCtrl::ExportToMenuButton  
 Metni araç çubuğu düğmesinden menü kopyalar.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *menuButton*  
 Hedef menü düğmesi referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) denetimi komut kimliği ile ilişkili dize kaynağı yüklenirken tarafından. Dize kaynakları hakkında daha fazla bilgi için bkz: [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).  
  
##  <a name="getbycmd"></a>  CMFCToolBarDateTimeCtrl::GetByCmd  
 İlk alır `CMFCToolBarDateTimeCtrl` belirtilen komut kimliği olan uygulama nesnesinde  
  
```  
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Komut Kimliği almak düğmesinin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk `CMFCToolBarDateTimeCtrl` belirtilen komut kimliği olan uygulama nesnesinde veya `NULL` yoksa `CMFCToolBarDateTimeCtrl` nesneler sahip belirtilen komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu paylaşılan yardımcı yöntem yöntemler tarafından da kullanılır [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) ve [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) ayarlamak veya saat ve tarih saat tüm örneklerinin almak için Belirtilen komut kimliği olması seçici denetimi  
  
##  <a name="getdatetimectrl"></a>  CMFCToolBarDateTimeCtrl::GetDateTimeCtrl  
 Bir işaretçi tarih ve Saat Seçici denetimine döndürür.  
  
```  
CDateTimeCtrl* GetDateTimeCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarih ve Saat Seçici denetimine işaretçi; veya `NULL` denetimi mevcut değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCToolBarDateTimeCtrl` Sınıfı başlatır `m_pWndDateTime` eklediğinizde veri üyesi bir `CMFCToolBarDateTimeCtrl` bir araç çubuğu nesnesine.  
  
##  <a name="gethwnd"></a>  CMFCToolBarDateTimeCtrl::GetHwnd  
 Araç çubuğu düğmesi ile ilişkili bir pencere tanıtıcının alır.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarih ve saat araç çubuğu düğmesi ile ilişkili pencere işleyicisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) yöntemi.  
  
##  <a name="gettime"></a>  CMFCToolBarDateTimeCtrl::GetTime  
 Seçilen zaman ilişkili tarih ve Saat Seçici denetimini alır ve belirtilen yerleştirir [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) yapısı  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *timeDest*  
 İlk aşırı içinde bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) sistem zamanı bilgileri alacak nesnesi. İkinci aşırı içinde bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) sistem zamanı bilgileri alacak nesnesi.  
  
 [out] *pTimeDest*  
 Bir işaretçi [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) sistem zamanı bilgileri almak için yapısı. Olmamalıdır `NULL`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zaman başarıyla yazılır, sıfır olmayan ilk aşırı içinde [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) nesne; Aksi takdirde 0. İkinci ve üçüncü aşırı dönüş değeri olan bir `DWORD` belirlenip dwFlag üye eşit olan [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem kümeleri [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) yapı üyesi dwFlags tarih ve Saat Seçici bir tarih ve saat için ayarlanmış olup olmadığını gösterir. Değer GDT_NONE eşitse denetimi kümesine `no date` durumu ve DTS_SHOWNONE stili kullanır. Döndürülen değer GDT_VALID eşitse, sistem saatini başarıyla hedef konumda depolanır.  
  
##  <a name="gettimeall"></a>  CMFCToolBarDateTimeCtrl::GetTimeAll  
 Belirtilen komut kimliğine sahip süresi Seçici denetim düğmesi kullanıcı tarafından seçilen saati döndürür  
  
```  
static BOOL GetTimeAll(
    UINT uiCmd,  
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeDest);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Araç çubuğu düğmesi 's komut kimliğini belirtir.  
  
 [out] *timeDest*  
 İlk aşırı içinde bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) sistem zamanı bilgileri alacak nesnesi. İkinci aşırı içinde bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) sistem zamanı bilgileri alacak nesnesi.  
  
 [out] *pTimeDest*  
 Bir işaretçi [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) sistem zamanı bilgileri almak için yapısı. Olmamalıdır `NULL`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Framework komut kimliği ile eşleşen bir araç çubuğu düğmesi bulamazsa *uiCmd*, dönüş değeri ilk aşırı sıfır ve diğer aşırı yüklemeler GDT_NONE değeridir. Araç çubuğu düğmesi bulunursa, dönüş değeri çağrısından dönüş değeri aynıdır [CMFCToolBarDateTimeCtrl::GetTime](#gettime) bu düğmesine. Dönüş değeri sıfır veya GDT_NONE düğmesi, hangi belirten bulunduğunda oluşabilir çağrısı `GetTime` başka bir nedenle için geçerli bir tarih döndürmedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrılarını ve belirtilen komut kimliği olan bir araç çubuğu düğmesi için görünür [CMFCToolBarDateTimeCtrl::GetTime](#gettime) bu düğmesine yöntemi.  
  
##  <a name="havehotborder"></a>  CMFCToolBarDateTimeCtrl::HaveHotBorder  
 Bir kullanıcı düğmesini seçtiğinde düğmesinin kenarlık görüntülenip görüntülenmeyeceğini belirler.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme seçildiğinde kenarlığını görüntülerse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, denetimi görünür durumdaysa sıfır olmayan bir değer döndürür.  
  
##  <a name="notifycommand"></a>  CMFCToolBarDateTimeCtrl::NotifyCommand  
 Düğme işler olup olmadığını belirtir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) ileti.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iNotifyCode*  
 Komutu ile ilişkili bildirim iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Düğme WM_COMMAND ileti işlediğinde veya `FALSE` iletinin üst araç tarafından işlenmiş olduğunu belirtmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Göndermek üzere olduğunda framework bu metodu çağıran bir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) üst pencere iletisi.  
  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) işleme tarafından [dtn_datetımechange](http://msdn.microsoft.com/library/windows/desktop/bb761737) bildirim. İç saat durumunu güncelleştirir ve süresi özelliği tüm güncelleştirmeleri `CMFCToolBarDateTimeCtrl` nesneleri aynı komut kimliği.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarDateTimeCtrl::OnAddToCustomizePage  
 Düğme eklendiğinde çerçevesi tarafından çağrılır bir **Özelleştir** iletişim kutusu.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), göre ilk tarihten özellikleri kopyalama ve zaman içinde bu nesnenin aynı komutu Kimliğine sahip herhangi bir araç çubuğu denetimi. Bu nesne ile aynı komut Kimliğine sahip bir tarih ve saat denetim hiçbir araç varsa, bu yöntem hiçbir şey yapmaz.  
  
 Hakkında daha fazla bilgi için **Özelleştir** iletişim kutusu, bkz: [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarDateTimeCtrl::OnChangeParentWnd  
 Yeni bir araç çubuğu düğmesi takıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Yeni üst pencere.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) iç yeniden tarafından `CMFCToolBarDateTimeCtrlImpl` nesnesi.  
  
##  <a name="onclick"></a>  CMFCToolBarDateTimeCtrl::OnClick  
 Kullanıcı denetimi tıklattığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Kullanılmayan.  
  
 [in] *bDelay*  
 Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin click ileti işlediğinde sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), sıfır olmayan bir değer varsa döndürerek iç `CMFCToolBarDateTimeCtrlImpl` nesnesidir görünür.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarDateTimeCtrl::OnCtlColor  
 Üst araç WM_CTLCOLOR iletisi işlediğinde çerçevesi tarafından çağrılır.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Düğme görüntüler cihaz bağlamı.  
  
 [in] *nCtlColor*  
 Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve arka düğmesinin boyamak için kullanır genel fırça için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), göre metin ayarlama ve arka plan genel metin sağlanan cihaz bağlamına renk ve arka plan renklerini, sırasıyla.  
  
 Uygulamanız için kullanılabilen genel seçenekleri hakkında daha fazla bilgi için bkz: [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged  
 Genel yazı tipi değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)), genel yazı tipi yazı tipini denetimi değiştirerek.  
  
 Uygulamanız için kullanılabilen genel seçenekleri hakkında daha fazla bilgi için bkz: [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>  CMFCToolBarDateTimeCtrl::OnMove  
 Üst araç taşındığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem varsayılan sınıf uygulaması geçersiz kılar ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) iç konumunu güncelleştirerek `CMFCToolBarDateTimeCtrlImpl` nesnesi.  
  
##  <a name="onshow"></a>  CMFCToolBarDateTimeCtrl::OnShow  
 Düğme olduğunda görünür veya görünmez çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bBilgi Göster*  
 Düğmenin görünür olup olmadığını belirtir. Bu parametre ise `TRUE`, düğmesi görünür. Aksi takdirde düğmesi görünür değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), düğme görüntüleyerek *bBilgi Göster* olan `TRUE`. Aksi takdirde, bu yöntem düğmesini gizler.  
  
##  <a name="onsize"></a>  CMFCToolBarDateTimeCtrl::OnSize  
 Üst araç boyutuna değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek için düğmesini çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iSize*  
 Yeni genişliğini piksel cinsinden düğmenin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem varsayılan sınıf uygulaması geçersiz kılar ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) boyutunu ve konumunu iç güncelleştirerek `CMFCToolBarDateTimeCtrlImpl` nesnesi.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarDateTimeCtrl::OnUpdateToolTip  
 Üst araç çubuğu araç ipucu metni güncelleştirdiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Üst pencere.  
  
 [in] *iButtonIndex*  
 Üst düğmesi koleksiyonundaki düğmesi sıfır tabanlı dizini.  
  
 [in] *wndToolTip*  
 Araç İpucu metni görüntüleyen denetim.  
  
 [out] *str*  
 A `CString` güncelleştirilmiş araç ipucu metni alan nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu metni yöntemi güncelleştirmeleri olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) görüntüleyerek düğmesi ile ilişkili araç ipucu metni. Bu yöntem düğmesi yatay yuvalanmış değilse, hiçbir şey yapmaz ve döndürür `FALSE`.  
  
##  <a name="settime"></a>  CMFCToolBarDateTimeCtrl::SetTime  
 Tarih ve Saat Seçici denetiminde ayarlar.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *timeNew*  
 İlk sürümünde, bir başvuru bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) olduğu denetimi ayarlanacak saati içeren nesne. İkinci sürümünde, bir işaretçi bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) olduğu denetimi ayarlanacak saati içeren nesne.  
  
 [in] *pTimeNew*  
 Bir işaretçi [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) olduğu denetimi ayarlanacak saati içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak bir tarih ve Saat Seçici denetiminde süreyi ayarlar [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).  
  
##  <a name="settimeall"></a>  CMFCToolBarDateTimeCtrl::SetTimeAll  
 Tarih ve saat belirtilen komut kimliği olan tüm örneklerine Saat Seçici denetimini ayarlar  
  
```  
static BOOL SetTimeAll(
    UINT uiCmd,  
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Araç çubuğu düğmesi 's komut kimliğini belirtir.  
  
 [in] *timeNew*  
 İlk sürümünde, bir [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md) olduğu denetimi ayarlanacak saati içeren nesne. İkinci sürümünde, bir işaretçi bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) olduğu denetimi ayarlanacak saati içeren nesne.  
  
 [in] *pTimeNew*  
 Bir işaretçi [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) olduğu denetimi ayarlanacak saati içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen komut Kimliğine sahip bir araç çubuğu düğmesi arar ve çağırarak bir tarih ve Saat Seçici denetiminde süreyi ayarlar [CMFCToolBarDateTimeCtrl::SetTime](#settime).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



