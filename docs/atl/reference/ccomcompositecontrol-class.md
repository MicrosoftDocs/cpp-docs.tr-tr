---
title: "CComCompositeControl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
dev_langs: C++
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2a7d7b14d67a127fadd8199f9cf9e1e209b8eea7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl sınıfı
Bu sınıf bileşik denetim uygulamak için gereken yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)bileşik denetim için desteklemek istediğiniz iyi herhangi diğer arabirimleri uğradıysa gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Oluşturucu.|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Öneri veya bileşik denetim tarafından barındırılan tüm denetimler unadvise için bu yöntemi çağırın.|  
|[CComCompositeControl::CalcExtent](#calcextent)|Boyutu hesaplamak için bu yöntemi çağırın **HIMETRIC** bileşik denetim barındırmak için kullanılan iletişim kaynak ölçü.|  
|[CComCompositeControl::Create](#create)|Bileşik Denetim denetimi penceresi oluşturmak için bu yöntem çağrılır.|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Denetimi penceresi oluşturun ve herhangi bir barındırılan denetimi bildirmek için bu yöntemi çağırın.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Kapsayıcının arka plan rengini kullanarak bileşik denetim arka plan rengini ayarlamak için bu yöntemi çağırın.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Arka plan Fırçası.|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Şu anda odağa sahip pencere işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfından türetilmiş sınıfları `CComCompositeControl` ActiveX bileşik denetim işlevselliğini devralır. ActiveX denetimleri türetilmiş `CComCompositeControl` standart iletişim kutusu tarafından barındırılır. Bu tür denetimler, diğer denetimler (yerel Windows denetimleri ve ActiveX denetimlerini) barındırabilen olduklarından bileşik denetimler adı verilir.  
  
 `CComCompositeControl`bir alt sınıfı numaralandırılmış veri üyesi arayarak bileşik denetim oluşturmak için iletişim kutusu kaynağı tanımlar. Bu alt sınıfın IDD üye denetimin pencere olarak kullanılacak iletişim kaynağının kaynak kimliği ayarlanır. Aşağıdaki sınıf türetilmiş veri üyesi örneğidir `CComCompositeControl` denetimin penceresi için kullanılacak iletişim kutusu kaynağı tanımlamak için içermelidir:  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Penceresiz denetimlerini içerebilir, ancak bileşik denetimler pencereli denetimleri, her zaman bulunur.  
  
 Bir denetimi tarafından uygulanan bir `CComCompositeControl`-türetilmiş sınıf varsayılan davranışı yerleşik sekme vardır. Denetim için içeren bir uygulamada sekmeli tarafından odağı aldığında, sırayla SEKME tuşuna basarak odağı aracılığıyla tüm bileşik denetim kapsanan denetimlerin sonra bileşik denetim dışında ve sonraki öğesinde açın geçiş sırasında neden olur kapsayıcının sekme sırası. Barındırılan denetimlerin sekme sırasını iletişim kaynak tarafından belirlenir ve sırasını belirler hangi sekme meydana gelir.  
  
> [!NOTE]
>  İle düzgün çalışması Hızlandırıcıları sırada bir `CComCompositeControl`, Denetim oluşturuldu olarak Hızlandırıcı tablosunu yüklenemedi, tanıtıcı ve Hızlandırıcıları uygulamasına geri sayısını geçirmek için gerekli [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), ve Son olarak denetimi yayımlandığında tablo yok.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="advisesinkmap"></a>CComCompositeControl::AdviseSinkMap  
 Öneri veya bileşik denetim tarafından barındırılan tüm denetimler unadvise için bu yöntemi çağırın.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAdvise`  
 Tüm denetimler tavsiye gerekiyorsa true; Aksi takdirde false.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`  
 Tüm havuz harita bağlı veya kendi olay kaynağından bağlantısı başarıyla kesildi durumunda denetler.  
  
 **E_FAIL**  
 Tüm havuz harita bağlı veya kendi olay kaynağından bağlantısı başarıyla kesildi durumunda denetler.  
  
 `E_POINTER`  
 Bu hata genellikle bir denetimin olay havuz eşleme girişi ile ilgili bir sorun ya da kullanılan şablon bağımsız değişken ile ilgili bir sorun gösterir bir `IDispEventImpl` veya `IDispEventSimpleImpl` temel sınıfı.  
  
 **CONNECT_E_ADVISELIMIT**  
 Bağlantı noktası zaten bağlantı sınırına ulaştı ve daha fazla kabul edemez.  
  
 **CONNECT_E_CANNOTCONNECT**  
 Havuz, bu bağlantı noktası tarafından gerekli arabirimi desteklemiyor.  
  
 **CONNECT_E_NOCONNECTION**  
 Tanımlama bilgisi değeri geçerli bir bağlantı göstermiyor. Bu hata genellikle bir denetimin olay havuz eşleme girişi ile ilgili bir sorun ya da kullanılan şablon bağımsız değişken ile ilgili bir sorun gösterir bir `IDispEventImpl` veya `IDispEventSimpleImpl` temel sınıfı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin temel uygulamayı girişlerini gözden olay havuz eşlemeyi arar. Öneren veya olay havuz haritanın havuz girdileri tarafından açıklanan COM nesneleri için bağlantı noktaları unadvises. Bu üye yöntemi de türetilmiş bir sınıf örneğinden devralır olgu kullanır `IDispEventImpl` tavsiye edilir veya unadvised olacak havuz eşlemesindeki her denetim için.  
  
##  <a name="calcextent"></a>CComCompositeControl::CalcExtent  
 Boyutu hesaplamak için bu yöntemi çağırın **HIMETRIC** bileşik denetim barındırmak için kullanılan iletişim kaynak ölçü.  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 Bir başvuru bir **BOYUTU** bu yöntem tarafından doldurulacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim bir iletişim kutusu tarafından barındırılıyorsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Boyutu döndürülür `size` parametresi.  
  
##  <a name="create"></a>CComCompositeControl::Create  
 Bileşik Denetim denetimi penceresi oluşturmak için bu yöntem çağrılır.  
  
```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 Denetimin üst pencere için bir tanıtıcı.  
  
 `rcPos`  
 Ayrılmış.  
  
 `dwInitParam`  
 Denetim oluşturma sırasında denetime geçirilecek veriler. Veri olarak geçirilen `dwInitParam` olarak gösterilir **LPARAM** parametresinin [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) oluşturulan bağlandığınızda bileşik denetim gönderilecek ileti.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan bileşik denetim iletişim kutusu için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem genellikle denetimi yerinde etkinleştirme sırasında çağrılır.  
  
##  <a name="ccomcompositecontrol"></a>CComCompositeControl::CComCompositeControl  
 Oluşturucu.  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır [CComCompositeControl::m_hbrBackground](#m_hbrbackground) ve [CComCompositeControl::m_hWndFocus](#m_hwndfocus) veri üyeleri null.  
  
##  <a name="dtor"></a>CComCompositeControl:: ~ CComCompositeControl  
 Yok Edicisi.  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa, arka plan nesneyi siler.  
  
##  <a name="createcontrolwindow"></a>CComCompositeControl::CreateControlWindow  
 Denetimi penceresi oluşturun ve tüm barındırılan denetimlerinin bildirmek için bu yöntemi çağırın.  
  
```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 Denetimin üst pencere için bir tanıtıcı.  
  
 `rcPos`  
 Bileşik Denetim İstemcisi'nde konumu dikdörtgen koordinatları göreli `hWndParent`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan bileşik denetim iletişim kutusu için bir işleyici döner.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [CComCompositeControl::Create](#create) ve [CComCompositeControl::AdviseSinkMap](#advisesinkmap).  
  
##  <a name="m_hbrbackground"></a>CComCompositeControl::m_hbrBackground  
 Arka plan Fırçası.  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>CComCompositeControl::m_hWndFocus  
 Şu anda odağa sahip pencere işleci.  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>CComCompositeControl::SetBackgroundColorFromAmbient  
 Kapsayıcının arka plan rengini kullanarak bileşik denetim arka plan rengini ayarlamak için bu yöntemi çağırın.  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Bileşik Denetim temelleri](../../atl/atl-composite-control-fundamentals.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
