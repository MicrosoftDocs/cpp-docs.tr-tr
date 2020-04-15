---
title: CComCompositeControl Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
ms.openlocfilehash: 700a8047ab1fa9df85c8e6530eb3eed5f29bd3d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320800"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl Sınıfı

Bu sınıf, bileşik denetim uygulamak için gereken yöntemleri sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra bileşik denetiminiz için desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomCompositeControl::ccomcompositecontrol](#ccomcompositecontrol)|Oluşturucu.|
|[CcomCompositeControl::~CcomcompositeControl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomCompositeControl::AdvisesinkMap](#advisesinkmap)|Kompozit denetim tarafından barındırılan tüm denetimleri tavsiye etmek veya tavsiye etmemek için bu yöntemi arayın.|
|[CComCompositeControl::CalcExtent](#calcextent)|Bileşik denetimi barındırmak için kullanılan iletişim kaynağının HIMETRIC birimlerindeki boyutunu hesaplamak için bu yöntemi arayın.|
|[CcomCompositeControl::Oluştur](#create)|Bu yöntem, bileşik denetim için denetim penceresi oluşturmak için denir.|
|[CcomCompositeControl::CreateControl Window](#createcontrolwindow)|Denetim penceresini oluşturmak için bu yöntemi arayın ve barındırılan denetimleri bildirin.|
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Kapsayıcının arka plan rengini kullanarak bileşik denetimin arka plan rengini ayarlamak için bu yöntemi arayın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Arka plan fırçası.|
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Şu anda odaklanmış olan pencerenin tutamacı.|

## <a name="remarks"></a>Açıklamalar

Sınıftan `CComCompositeControl` türetilen sınıflar activex bileşik denetiminin işlevselliğini devralır. Türeyen `CComCompositeControl` ActiveX denetimleri standart bir iletişim kutusu tarafından barındırılır. Diğer denetimleri (yerel Windows denetimleri ve ActiveX denetimleri) barındırabildiklerinden bu tür denetimlere bileşik denetimler denir.

`CComCompositeControl`alt sınıfta numaralandırılmış bir veri üyesi arayarak bileşik denetim oluştururken kullanılacak iletişim kaynağını tanımlar. Bu alt sınıfın üye IDD'si, denetim penceresi olarak kullanılacak iletişim kaynağının kaynak kimliğine ayarlanır. Denetim penceresi için kullanılacak iletişim kaynağını tanımlamak `CComCompositeControl` için sınıfın içermesi gereken veri üyesinin bir örneği aşağıda verilmiştir:

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
> Bileşik denetimler her zaman pencereli denetimlerdir, ancak penceresiz denetimler içerebilirler.

Türetilmiş bir `CComCompositeControl`sınıf tarafından uygulanan bir denetim, yerleşik varsayılan sekme davranışı vardır. Denetim, içeren bir uygulamada sekmeli olarak netlik aldığında, TAB tuşuna art arda basıldığında, odağın bileşik denetimin içerdiği tüm denetim denetimleri üzerinden, daha sonra bileşik denetimin dışına ve kapsayıcının sekme sırasına göre bir sonraki öğeye geçmesine neden olur. Barındırılan denetimlerin sekme sırası iletişim kaynağı tarafından belirlenir ve sekmelerin oluşacağı sırayı belirler.

> [!NOTE]
> Hızlandırıcıların bir `CComCompositeControl`ile düzgün çalışabilmesi için, kontrol oluşturulduğunda bir hızlandırıcı tablosuyüklemek, kolu ve hızlandırıcı sayısını [IOleControlImpl::GetControlInfo'ya](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)geri geçirmek ve kontrol serbest bırakıldığında nihayet tabloyu yok etmek gerekir.

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WinBase`

[CcomControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CcomControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ccomcompositecontroladvisesinkmap"></a><a name="advisesinkmap"></a>CcomCompositeControl::AdvisesinkMap

Kompozit denetim tarafından barındırılan tüm denetimleri tavsiye etmek veya tavsiye etmemek için bu yöntemi arayın.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*bAdvise*<br/>
Tüm kontroller tavsiye edilecekse doğrudur; aksi takdirde yanlış.

### <a name="return-value"></a>Dönüş Değeri

|||
|-|-|
|S_OK  |Olay lavabo haritasındaki tüm denetimler olay kaynağından başarıyla bağlandı veya bağlantıkesildi.|
|E_faıl  |Olay lavabo haritasındaki tüm denetimler olay kaynağından başarıyla bağlanamayabilir veya bağlantıkesilemedi.|
|E_POINTER  |Bu hata genellikle denetimin olay lavabo haritasındaki bir girişle veya bir `IDispEventImpl` veya `IDispEventSimpleImpl` taban sınıfta kullanılan şablon bağımsız değişkeniyle ilgili bir sorunu gösterir.|
|CONNECT_E_ADVISELIMIT  |Bağlantı noktası zaten bağlantı sınırına ulaştı ve daha fazlasını kabul edemiyor.|
|CONNECT_E_CANNOTCONNECT  |Lavabo, bu bağlantı noktasının gerektirdiği arabirimi desteklemez.|
|CONNECT_E_NOCONNECTION  |Çerez değeri geçerli bir bağlantıyı temsil etmez. Bu hata genellikle denetimin olay lavabo haritasındaki bir girişle veya bir `IDispEventImpl` veya `IDispEventSimpleImpl` taban sınıfta kullanılan şablon bağımsız değişkeniyle ilgili bir sorunu gösterir.|

### <a name="remarks"></a>Açıklamalar

Bu yöntemin temel uygulaması, olay lavabo haritasındaki girişler aracılığıyla arama lar. Daha sonra, olay lavabo haritasının lavabo girişleri tarafından açıklanan COM nesnelerine bağlantı noktalarını önerir veya tavsiye etmeyiz. Bu üye yöntemi aynı zamanda, türetilen sınıfın, bilgi `IDispEventImpl` verilmesi veya tavsiye edilmemesi gereken lavabo haritasındaki her denetim için bir örnekten devralınmasına da dayanır.

## <a name="ccomcompositecontrolcalcextent"></a><a name="calcextent"></a>CComCompositeControl::CalcExtent

Bileşik denetimi barındırmak için kullanılan iletişim kaynağının HIMETRIC birimlerindeki boyutunu hesaplamak için bu yöntemi arayın.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Bu yöntemle `SIZE` doldurulacak bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Denetim bir iletişim kutusu tarafından barındırılan varsa TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Boyut parametresinde *size* döndürülür.

## <a name="ccomcompositecontrolcreate"></a><a name="create"></a>CcomCompositeControl::Oluştur

Bu yöntem, bileşik denetim için denetim penceresi oluşturmak için denir.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Denetimin üst penceresine bir tutamaç.

*rcPos*<br/>
Ayrılmış.

*dwInitParam*<br/>
Denetim oluşturma sırasında denetime aktaredilecek veriler. *dwInitParam* olarak geçirilen veriler, [oluşturulduğunda](/windows/win32/dlgbox/wm-initdialog) bileşik denetime gönderilecek olan WM_INITDIALOG iletisinin LPARAM parametresi olarak gösterecektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bileşik denetim iletişim kutusuna bir tutamaç.

### <a name="remarks"></a>Açıklamalar

Bu yöntem genellikle denetimin yerinde aktivasyonu sırasında çağrılır.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="ccomcompositecontrol"></a>CcomCompositeControl::ccomcompositecontrol

Oluşturucu.

```
CComCompositeControl();
```

### <a name="remarks"></a>Açıklamalar

[CComCompositeControl::m_hbrBackground](#m_hbrbackground) ve [CComCompositeControl::m_hWndFocus](#m_hwndfocus) veri üyelerini NULL'a karşı başharfe aktarın.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="dtor"></a>CcomCompositeControl::~CcomcompositeControl

Yıkıcı.

```
~CComCompositeControl();
```

### <a name="remarks"></a>Açıklamalar

Varsa arka plan nesnesini siler.

## <a name="ccomcompositecontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>CcomCompositeControl::CreateControl Window

Denetim penceresini oluşturmak ve barındırılan denetimleri bildirmek için bu yöntemi arayın.

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Denetimin üst penceresine bir tutamaç.

*rcPos*<br/>
Istemci koordinatlarında bileşik denetimin konum dikdörtgeni *hWndParent*göreli .

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bileşik denetim iletişim kutusuna bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [ccomCompositeControl çağırır::Oluştur](#create) ve [CComCompositeControl::AdviseSinkMap](#advisesinkmap).

## <a name="ccomcompositecontrolm_hbrbackground"></a><a name="m_hbrbackground"></a>CComCompositeControl::m_hbrBackground

Arka plan fırçası.

```
HBRUSH m_hbrBackground;
```

## <a name="ccomcompositecontrolm_hwndfocus"></a><a name="m_hwndfocus"></a>CComCompositeControl::m_hWndFocus

Şu anda odaklanmış olan pencerenin tutamacı.

```
HWND m_hWndFocus;
```

## <a name="ccomcompositecontrolsetbackgroundcolorfromambient"></a><a name="setbackgroundcolorfromambient"></a>CComCompositeControl::SetBackgroundColorFromAmbient

Kapsayıcının arka plan rengini kullanarak bileşik denetimin arka plan rengini ayarlamak için bu yöntemi arayın.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Kompozit Kontrol Esasları](../../atl/atl-composite-control-fundamentals.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
