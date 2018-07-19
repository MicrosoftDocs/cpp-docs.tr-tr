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
ms.openlocfilehash: 77b0c115dbd820ea715b739dd3e4d6eb2c5f4950
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883456"
---
# <a name="ccomcontrol-class"></a>CComControl sınıfı
Bu sınıf, oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Denetimi uygulamak sınıfı.  
  
 *WinBase*  
 Pencereleme işlevleri uygulayan temel sınıf. Varsayılan olarak [Cwindowımpl](../../atl/reference/cwindowimpl-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|Denetim için bir pencere oluşturur.|  
|[CComControl::FireOnChanged](#fireonchanged)|Denetimine özelliğin değiştirildiğini kapsayıcının havuz bildirir.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Kapsayıcının havuz nesne nasıl devam etmek havuz isteyen ve bir denetim özelliği değişmek üzere olduğunu bildirir.|  
|[CComControl::MessageBox](#messagebox)|Oluşturun, görüntüleyin ve bir ileti kutusu çalışması için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComControl` faydalı bir denetim yardımcı işlevleri ve ATL denetimleri için gerekli veri üyeleri kümesidir. Standart bir denetimde veya ATL Denetim Sihirbazı'nı kullanarak bir DHTML denetimi oluşturduğunuzda, sihirbaz sizin sınıfınızdan otomatik olarak derleyeceği `CComControl`. `CComControl` Bunun yöntemlerinden çoğunu türetilen [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Bir denetim oluşturma hakkında daha fazla bilgi için bkz. [ATL öğretici](../../atl/active-template-library-atl-tutorial.md). ATL projesi Sihirbazı hakkında daha fazla bilgi için bkz [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).  
  
 Tanıtımı için `CComControl` yöntemleri ve veri üyeleri [DAİ](../../visual-cpp-samples.md) örnek.  
  
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
 Çağrıları [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) geçirme Oluşturucusu `m_hWnd` veri üyesi devralınan aracılığıyla [Cwindowımpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>  CComControl::ControlQueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] İstenen arabiriminin GUID'si.  
  
 *ppv*  
 [out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*, veya arabirim bulunamazsa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 yalnızca COM eşleme tablosunda arabirimleri işler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>  CComControl::CreateControlWindow  
 Varsayılan olarak, çağırarak denetimi için bir pencere oluşturur. `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWndParent*  
 [in] Üst veya sahibi penceresine işleyin. Geçerli pencere tanıtıcısı sağlanmalıdır. Denetimi pencerenin üst pencereye bölgesine sınırlıdır.  
  
 *rcPos*  
 [in] Oluşturulacak pencerenin konumunu ve ilk boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir şey yapmak istiyorsanız bu yöntemi yok sayın. tek bir pencere dışında oluşturun, örneğin, iki windows oluşturmak için biri denetiminiz için bir araç haline gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>  CComControl::FireOnChanged  
 Denetimine özelliğin değiştirildiğini kapsayıcının havuz bildirir.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dispID*  
 [in] Değişen özellik tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfınıza türetildiği varsa [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638), bu yöntemin çağırdığı [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) tüm bildirmek için bağlı `IPropertyNotifySink` , arabirimleri belirtilen Denetim özellik değişti. Denetim sınıfınıza türünden türemez varsa `IPropertyNotifySink`, bu yöntem S_OK döndürür. 
  
 Bu yöntem, denetim bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>  CComControl::FireOnRequestEdit  
 Kapsayıcının havuz nesne nasıl devam etmek havuz isteyen ve bir denetim özelliği değişmek üzere olduğunu bildirir.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dispID*  
 [in] Değişmek üzere özellik tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfınıza türetildiği varsa [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638), bu yöntemin çağırdığı [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) tüm bildirmek için bağlı `IPropertyNotifySink` , arabirimleri belirtilen Denetim özelliği hakkında değiştirmektir. Denetim sınıfınıza türünden türemez varsa `IPropertyNotifySink`, bu yöntem S_OK döndürür.  

  
 Bu yöntem, denetim bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>  CComControl::MessageBox  
 Oluşturun, görüntüleyin ve bir ileti kutusu çalışması için bu yöntemi çağırın.  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszText*  
 İleti kutusunda görüntülenecek metin.  
  
 *lpszCaption*  
 İletişim kutusu başlığı. Değilse boş (varsayılan), başlığı "Error" kullanılır.  
  
 *nTür*  
 İçeriği ve iletişim kutusunu davranışını belirtir. Bkz: [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) kullanılabilir farklı ileti kutuları bir listesi için Windows SDK belgelerine girişi. Basit bir varsayılan sağlar **Tamam** düğmesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir menü öğesi altında listelenen değerleri belirten bir tamsayı değeri döndürür [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) Windows SDK belgelerinde.  
  
### <a name="remarks"></a>Açıklamalar  
 `MessageBox` Geliştirme sırasında ve bir hata veya uyarı iletisini kullanıcıya göstermek için kolay bir yol olarak yararlı olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cwindowımpl sınıfı](../../atl/reference/cwindowimpl-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [CComControlBase sınıfı](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl Sınıfı](../../atl/reference/ccomcompositecontrol-class.md)
