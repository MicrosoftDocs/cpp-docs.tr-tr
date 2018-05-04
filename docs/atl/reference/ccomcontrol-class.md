---
title: CComControl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
dev_langs:
- C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6017d06715146a0440887a2a2e10828398d5044b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcontrol-class"></a>CComControl sınıfı
Bu sınıf oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Denetim uygulayan sınıfa.  
  
 *WinBase*  
 Pencereleme işlevleri uygulayan temel sınıf. Varsayılan olarak [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|Denetimi için pencere oluşturur.|  
|[CComControl::FireOnChanged](#fireonchanged)|Bir denetim özelliği değişti kapsayıcının havuz bildirir.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Kapsayıcının havuz denetim özelliğini değiştirilmek üzere olduğunu ve nesne nasıl ilerleyeceğiniz havuz isteyen bildirir.|  
|[CComControl::MessageBox](#messagebox)|Oluşturun, görüntüleyin ve bir ileti kutusu çalıştırmak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComControl` kullanışlı denetimi yardımcı işlevleri ve ATL denetimleri için temel veri üyeleri kümesidir. Standart bir denetimde veya ATL Denetim Sihirbazı'nı kullanarak bir DHTML denetimi oluşturduğunuzda, sihirbaz otomatik olarak, sınıfından türetilen `CComControl`. `CComControl` kendi yöntemleri çoğunu türetilen [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Bir denetim oluşturma hakkında daha fazla bilgi için bkz: [ATL öğretici](../../atl/active-template-library-atl-tutorial.md). ATL Proje Sihirbazı hakkında daha fazla bilgi için bkz: [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).  
  
 Tanıtımı için `CComControl` yöntemleri ve veri üyeleri bkz [DAİ](../../visual-cpp-samples.md) örnek.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="ccomcontrol"></a>  CComControl::CComControl  
 Oluşturucu.  
  
```
CComControl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) geçirme Oluşturucusu `m_hWnd` veri üyesi devralınan aracılığıyla [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>  CComControl::ControlQueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İstenen arabirimi GUID.  
  
 `ppv`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `iid`, veya **NULL** arabirimi bulunmazsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca COM eşleme tablosu arabirimlerde işler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>  CComControl::CreateControlWindow  
 Varsayılan olarak, denetimi için pencere çağırarak oluşturur `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 [in] Üst veya sahibi penceresine işleyin. Geçerli bir pencere tanıtıcının sağlanmalıdır. Denetimi penceresi kendi üst penceresi alanına sınırlıysa.  
  
 `rcPos`  
 [in] İlk boyutunu ve konumunu penceresinin oluşturulacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir şey yapmak istiyorsanız bu yöntemi geçersiz kılın dışında tek bir pencere oluşturma, örneğin, iki windows oluşturmak için bunlardan biri denetlemek için bir araç haline gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>  CComControl::FireOnChanged  
 Bir denetim özelliği değişti kapsayıcının havuz bildirir.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dispID*  
 [in] Değişti özellik tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfınıza türetilen varsa [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638), bu yöntemi çağırır [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) tüm bildirmek için bağlı `IPropertyNotifySink` , arabirimleri belirtilen Denetim özellik değişti. Denetim sınıfınıza türünden türemez varsa `IPropertyNotifySink`, bu yöntem `S_OK`. 
  
 Bu yöntem, denetim bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>  CComControl::FireOnRequestEdit  
 Kapsayıcının havuz denetim özelliğini değiştirilmek üzere olduğunu ve nesne nasıl ilerleyeceğiniz havuz isteyen bildirir.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dispID*  
 [in] Değiştirilmek özellik tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfınıza türetilen varsa [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638), bu yöntemi çağırır [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) tüm bildirmek için bağlı `IPropertyNotifySink` , arabirimleri belirtilen Denetim özelliği hakkında değiştirmektir. Denetim sınıfınıza türünden türemez varsa `IPropertyNotifySink`, bu yöntem `S_OK`.  

  
 Bu yöntem, denetim bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>  CComControl::MessageBox  
 Oluşturun, görüntüleyin ve bir ileti kutusu çalıştırmak için bu yöntemi çağırın.  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszText`  
 İleti kutusunda görüntülenecek metin.  
  
 `lpszCaption`  
 İletişim kutusu başlığı. Değilse NULL (varsayılan), "Error" kullanılır başlığı.  
  
 `nType`  
 İçeriği ve iletişim kutusunu davranışını belirtir. Bkz: [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) bir listesi için Windows SDK Belgeleri kullanılabilir farklı ileti kutularının girişi. Basit bir varsayılan sağlar **Tamam** düğmesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Altında listelenen menü öğesi değerlerden birini belirten bir tamsayı değeri döndürür [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) Windows SDK belgelerinde.  
  
### <a name="remarks"></a>Açıklamalar  
 `MessageBox` Geliştirme sırasında hem bir hata veya uyarı iletisi kullanıcıya görüntülenmesi için kolay bir yol olarak yararlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWindowImpl sınıfı](../../atl/reference/cwindowimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComControlBase sınıfı](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl Sınıfı](../../atl/reference/ccomcompositecontrol-class.md)
