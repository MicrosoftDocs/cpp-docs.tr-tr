---
title: CComCompositeControl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0622e939d1c0cb93579baeb5fa35e11be516e5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756580"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl sınıfı

Bu sınıf, bileşik denetim uygulamak için gereken yöntemleri sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>Parametreler

*T*  
Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer arabirimleri uğradıysa bileşik denetim için desteklemek istediğiniz gibi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Oluşturucu.|
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Bileşik denetim tarafından barındırılan tüm denetimleri eşlemesindeki önermek veya öneriyi kaldırmak için bu yöntemi çağırın.|
|[CComCompositeControl::CalcExtent](#calcextent)|Bileşik denetimini barındırmak için kullanılan iletişim kaynağını HIMETRIC birimleri cinsinden boyut hesaplamak için bu yöntemi çağırın.|
|[CComCompositeControl::Create](#create)|Bileşik denetim için Denetim pencere oluşturmak için bu yöntem çağrılır.|
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Denetimi penceresi oluştur ve herhangi bir denetimden bildirmek için bu yöntemi çağırın.|
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Kapsayıcının arka plan rengiyle bileşik denetim arka plan rengini ayarlamak için bu yöntemi çağırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Arka plan Fırçası.|
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|O anda odağı içeren pencere tanıtıcısı.|

## <a name="remarks"></a>Açıklamalar

Sınıfından türetilmiş sınıflar `CComCompositeControl` bileşik ActiveX denetiminin işlevselliğini devralır. ActiveX denetimleri türetilen `CComCompositeControl` standart iletişim kutusu tarafından barındırılır. Diğer denetimler (yerel Windows denetimlerini ve ActiveX denetimleri) barındırabilen olduğundan bu tür denetimler bileşik denetimler olarak adlandırılır.

`CComCompositeControl` bileşik denetimini alt sınıf bir numaralandırılmış veri üyesi arayarak oluştururken kullanılacak iletişim kutusu kaynağı tanımlar. Bu alt sınıfın IDD üye denetim pencere kullanılan iletişim kaynağını kaynak Kimliğine ayarlanır. Veri üyesi türetilmiş sınıfın bir örneği verilmiştir `CComCompositeControl` denetimin penceresi için kullanılan iletişim kaynağını belirlemek için içermelidir:

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
>  Penceresiz denetimleri içerebilse bileşik denetimler pencereli denetimler, her zaman değil.

Bir denetimi tarafından uygulanan bir `CComCompositeControl`-türetilmiş sınıfında varsayılan yerleşik davranış sekme. Denetim için içeren bir uygulamada sekmeli tarafından odağı aldığında, sırayla SEKME tuşuna basarak odağı tüm bileşik denetim içerdiği denetimlerle sonra bileşik denetimin dışına ve sonraki öğeyi açın yeniden sağlanıncaya neden olur kapsayıcının sekme sırası. Barındırılan denetimlerin sekme sırasını iletişim kaynak tarafından belirlenir ve sırasını belirleyen hangi sekme meydana gelir.

> [!NOTE]
>  Hızlandırıcıları düzgün şekilde çalışmak için sırayla bir `CComCompositeControl`, Denetim oluşturduğunda Hızlandırıcı tablosunu yüklenemedi, yeniden Hızlandırıcıları sayısı ve tanıtıcı geçirmek için gerekli [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), ve Son olarak denetim serbest bırakıldığında tablo yok.

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="advisesinkmap"></a>  CComCompositeControl::AdviseSinkMap

Bileşik denetim tarafından barındırılan tüm denetimleri eşlemesindeki önermek veya öneriyi kaldırmak için bu yöntemi çağırın.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*bAdvise*  
Tüm denetimleri tavsiye gerekiyorsa true; Aksi durumda false.

### <a name="return-value"></a>Dönüş Değeri

S_OK  
Tüm havuz harita bağlı veya kendi olay kaynağından bağlantısı başarıyla kesildi durumunda denetler.

E_FAIL  
Tüm havuz harita bağlı veya kendi olay kaynağından bağlantısı başarıyla kesildi durumunda denetler.

E_POINTER  
Bu hata genellikle bir giriş denetiminin olay havuzu eşlemesi ile ilgili bir sorun veya kullanılan bir şablon bağımsız değişkeni ile ilgili bir sorun gösterir bir `IDispEventImpl` veya `IDispEventSimpleImpl` temel sınıfı.

CONNECT_E_ADVISELIMIT  
Bağlantı noktası zaten bağlantı sınırına ulaştı ve daha fazla kabul edemez.

CONNECT_E_CANNOTCONNECT  
Havuz Bu bağlantı noktasınca istenen arabirimi desteklemiyor.

CONNECT_E_NOCONNECTION  
Tanımlama bilgisi değeri geçerli bir bağlantı temsil etmiyor. Bu hata genellikle bir giriş denetiminin olay havuzu eşlemesi ile ilgili bir sorun veya kullanılan bir şablon bağımsız değişkeni ile ilgili bir sorun gösterir bir `IDispEventImpl` veya `IDispEventSimpleImpl` temel sınıfı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin taban uygulamasını girişleri olay havuzu harita arar. Öneren veya olay havuzu haritanın havuz girdileri tarafından açıklanan COM nesneleri için bağlantı noktalarını unadvises. Bu üye yöntemi türetilmiş sınıfın bir örneğinden devralan gerçeği de dayanan `IDispEventImpl` tavsiye edilir veya unadvised olacak havuz eşlemesindeki her denetim için.

##  <a name="calcextent"></a>  CComCompositeControl::CalcExtent

Bileşik denetimini barındırmak için kullanılan iletişim kaynağını HIMETRIC birimleri cinsinden boyut hesaplamak için bu yöntemi çağırın.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*  
Bir başvuru bir `SIZE` yapısı bu yöntem tarafından doldurulmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Denetim bir iletişim kutusu tarafından barındırılıyorsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Boyutu döndürülür *boyutu* parametresi.

##  <a name="create"></a>  CComCompositeControl::Create

Bileşik denetim için Denetim pencere oluşturmak için bu yöntem çağrılır.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*  
Denetimin ana penceresine tanıtıcı.

*rcPos*  
Ayrılmış.

*dwInitParam*  
Denetim oluşturma sırasında denetime geçirilecek veriler. Veri olarak geçirilen *dwInitParam* LPARAM parametresi olarak görünür [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) oluşturulan, bileşik denetime gönderilecek ileti.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bileşik denetim iletişim kutusu için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem genellikle denetimin yerinde etkinleştirme sırasında çağrılır.

##  <a name="ccomcompositecontrol"></a>  CComCompositeControl::CComCompositeControl

Oluşturucu.

```
CComCompositeControl();
```

### <a name="remarks"></a>Açıklamalar

Başlatır [CComCompositeControl::m_hbrBackground](#m_hbrbackground) ve [CComCompositeControl::m_hWndFocus](#m_hwndfocus) veri üyeleri null.

##  <a name="dtor"></a>  CComCompositeControl:: ~ CComCompositeControl

Yıkıcı.

```
~CComCompositeControl();
```

### <a name="remarks"></a>Açıklamalar

Varsa arka plan nesneyi siler.

##  <a name="createcontrolwindow"></a>  CComCompositeControl::CreateControlWindow

Denetimi penceresi oluştur ve barındırılan herhangi bir denetim bildirmek için bu yöntemi çağırın.

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>Parametreler

*hWndParent*  
Denetimin ana penceresine tanıtıcı.

*rcPos*  
Bileşik Denetim istemcisinde konumu dikdörtgenin koordinatları göreli *hWndParent*.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bileşik denetim iletişim kutusu için bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [CComCompositeControl::Create](#create) ve [CComCompositeControl::AdviseSinkMap](#advisesinkmap).

##  <a name="m_hbrbackground"></a>  CComCompositeControl::m_hbrBackground

Arka plan Fırçası.

```
HBRUSH m_hbrBackground;
```

##  <a name="m_hwndfocus"></a>  CComCompositeControl::m_hWndFocus

O anda odağı içeren pencere tanıtıcısı.

```
HWND m_hWndFocus;
```

##  <a name="setbackgroundcolorfromambient"></a>  CComCompositeControl::SetBackgroundColorFromAmbient

Kapsayıcının arka plan rengiyle bileşik denetim arka plan rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
[Bileşik Denetim temelleri](../../atl/atl-composite-control-fundamentals.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
