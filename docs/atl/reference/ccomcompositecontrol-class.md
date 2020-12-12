---
description: 'Daha fazla bilgi edinin: CComCompositeControl sınıfı'
title: CComCompositeControl sınıfı
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
ms.openlocfilehash: 5c4d5b3e04855d570cab3a85bfe3a4c59482d990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146828"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl sınıfı

Bu sınıf, bileşik denetim uygulamak için gereken yöntemleri sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)'den türetilir ve bileşik denetiminiz için desteklemek istediğiniz diğer arabirimlerden de elde edersiniz.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCompositeControl:: CComCompositeControl](#ccomcompositecontrol)|Oluşturucu.|
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCompositeControl:: Advisesınkmap](#advisesinkmap)|Bileşik denetim tarafından barındırılan tüm denetimleri bildirmek veya çağırmak için bu yöntemi çağırın.|
|[CComCompositeControl:: Calckapsam](#calcextent)|Bileşik denetimi barındırmak için kullanılan iletişim kaynağının HIMETRIK birimlerindeki boyutu hesaplamak için bu yöntemi çağırın.|
|[CComCompositeControl:: Create](#create)|Bu yöntem, bileşik denetim için Denetim penceresini oluşturmak üzere çağırılır.|
|[CComCompositeControl:: CreateControlWindow](#createcontrolwindow)|Denetim penceresini oluşturmak ve tüm barındırılan denetimleri bildirmek için bu yöntemi çağırın.|
|[CComCompositeControl:: SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Kapsayıcının arka plan rengini kullanarak bileşik denetimin arka plan rengini ayarlamak için bu yöntemi çağırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCompositeControl:: m_hbrBackground](#m_hbrbackground)|Arka plan Fırçası.|
|[CComCompositeControl:: m_hWndFocus](#m_hwndfocus)|Şu anda odaklanmış pencerenin tutamacı.|

## <a name="remarks"></a>Açıklamalar

Sınıfından türetilmiş sınıflar `CComCompositeControl` bir ActiveX bileşik denetiminin işlevselliğini miras alır. İçinden türetilmiş ActiveX denetimleri `CComCompositeControl` , standart iletişim kutusuyla barındırılır. Bu tür denetimler, diğer denetimleri barındırabildiğinden (yerel Windows denetimleri ve ActiveX denetimleri) bileşik denetimler olarak adlandırılır.

`CComCompositeControl` alt sınıfta bir numaralandırılmış veri üyesini arayarak bileşik denetim oluşturma bölümünde kullanılacak iletişim kutusunu tanımlar. Bu alt sınıfın üye kimliği, denetimin penceresi olarak kullanılacak iletişim kaynağı kaynak kimliğine ayarlanır. Aşağıda, öğesinden türetilen sınıfın, `CComCompositeControl` denetimin penceresi için kullanılacak iletişim kaynağını belirlemek için içermesi gereken veri üyesine yönelik bir örnek verilmiştir:

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
> Bileşik denetimler her zaman pencereli denetimlerdir, ancak Penceresiz denetimler içerebilirler.

Türetilmiş bir sınıf tarafından uygulanan bir denetim `CComCompositeControl` , içinde yerleşik olarak bulunan varsayılan sekme davranışına sahiptir. Denetim odağı içeren bir uygulamada sekmeli olarak aldığında, sekme tuşuna büyük ölçüde basmak, odağın bileşik denetimin içerdiği denetimler ve sonra bileşik denetimin dışında ve kapsayıcının sekme düzeninde bir sonraki öğeye açılıp dağıtılmamasına neden olur. Barındırılan denetimlerin sekme sıralaması iletişim kaynağı tarafından belirlenir ve sekme 'nin gerçekleşeceği sırayı belirler.

> [!NOTE]
> Hızlandırıcının ile düzgün çalışması için `CComCompositeControl` , denetim oluşturulduğu için bir Hızlandırıcı tablosu yüklenmesi, hızlandırıcının tanıtıcısını ve sayısını [IOleControlImpl:: Getcontrolinınfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)içine geçirin ve son olarak denetim serbest bırakıldığında tabloyu yok edin.

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ccomcompositecontroladvisesinkmap"></a><a name="advisesinkmap"></a> CComCompositeControl:: Advisesınkmap

Bileşik denetim tarafından barındırılan tüm denetimleri bildirmek veya çağırmak için bu yöntemi çağırın.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*Rozzden*<br/>
Tüm denetimler önermeliyse doğru; Aksi halde yanlış.

### <a name="return-value"></a>Dönüş Değeri

| Değer | Açıklama |
|--|--|
| `S_OK` | Olay havuzu haritadaki tüm denetimler, Olay kaynağıyla başarıyla bağlandı veya bağlantısı kesildi. |
| `E_FAIL` | Olay havuzu haritadaki tüm denetimler, Olay kaynağıyla başarıyla bağlanmayabilir veya bağlantısı kesilemiyor. |
| `E_POINTER` | Bu hata genellikle, denetimin olay havuzu eşlemesindeki bir girdiyle veya bir `IDispEventImpl` veya temel sınıfta kullanılan şablon bağımsız değişkeniyle ilgili bir sorun olduğunu gösterir `IDispEventSimpleImpl` . |
| `CONNECT_E_ADVISELIMIT` | Bağlantı noktası zaten bağlantı sınırına ulaştı ve daha fazlasını kabul edemez. |
| `CONNECT_E_CANNOTCONNECT` | Havuz, bu bağlantı noktası için gereken arabirimi desteklemiyor. |
| `CONNECT_E_NOCONNECTION` | Tanımlama bilgisi değeri geçerli bir bağlantıyı temsil etmiyor. Bu hata genellikle, denetimin olay havuzu eşlemesindeki bir girdiyle veya bir `IDispEventImpl` veya temel sınıfta kullanılan şablon bağımsız değişkeniyle ilgili bir sorun olduğunu gösterir `IDispEventSimpleImpl` . |

### <a name="remarks"></a>Açıklamalar

Bu yöntemin temel uygulanması, olay havuzu haritalarındaki girdileri arar. Daha sonra, olay havuzu haritasının havuz girişleri tarafından tanımlanan COM nesnelerine bağlantı noktalarını önerir veya bunun üzerinde bir açıklama vermez. Bu üye yöntemi Ayrıca, türetilmiş sınıfın, bir `IDispEventImpl` veya tavsiye edilecek havuz eşlemesindeki her denetim için bir örneğinden devraldığından emin olur.

## <a name="ccomcompositecontrolcalcextent"></a><a name="calcextent"></a> CComCompositeControl:: Calckapsam

Bileşik denetimi barındırmak için kullanılan iletişim kaynağının HIMETRIK birimlerindeki boyutu hesaplamak için bu yöntemi çağırın.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
`SIZE`Bu yöntemle doldurulacak bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Denetim bir iletişim kutusu tarafından barındırılıyorsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Boyut, *Boyut* parametresinde döndürülür.

## <a name="ccomcompositecontrolcreate"></a><a name="create"></a> CComCompositeControl:: Create

Bu yöntem, bileşik denetim için Denetim penceresini oluşturmak üzere çağırılır.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Denetimin üst penceresine yönelik bir tanıtıcı.

*rcPos*<br/>
Ayrılmış.

*dwInitParam*<br/>
Denetim oluşturma sırasında denetime geçirilecek veriler. *Dwinitparam* olarak geçirilen veriler, oluşturulduğunda bileşik denetime gönderilecek [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) iletisinin lParam parametresi olarak gösterilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bileşik denetim iletişim kutusu için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem genellikle denetimin yerinde etkinleştirilmesi sırasında çağrılır.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="ccomcompositecontrol"></a> CComCompositeControl:: CComCompositeControl

Oluşturucu.

```
CComCompositeControl();
```

### <a name="remarks"></a>Açıklamalar

[CComCompositeControl:: m_hbrBackground](#m_hbrbackground) ve [ccomcompositecontrol:: M_HWNDFOCUS](#m_hwndfocus) veri üyelerini null olarak başlatır.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="dtor"></a> CComCompositeControl:: ~ CComCompositeControl

Yok edicisi.

```
~CComCompositeControl();
```

### <a name="remarks"></a>Açıklamalar

Varsa, arka plan nesnesini siler.

## <a name="ccomcompositecontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a> CComCompositeControl:: CreateControlWindow

Denetim penceresini oluşturmak için bu yöntemi çağırın ve tüm barındırılan denetimlere tavsiye edin.

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Denetimin üst penceresine yönelik bir tanıtıcı.

*rcPos*<br/>
İstemci koordinatlarındaki bileşik denetimin konum dikdörtgeni *hwndParent* göre.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bileşik denetim iletişim kutusuna bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CComCompositeControl:: Create](#create) ve [CComCompositeControl:: Advisesınkmap](#advisesinkmap)öğesini çağırır.

## <a name="ccomcompositecontrolm_hbrbackground"></a><a name="m_hbrbackground"></a> CComCompositeControl:: m_hbrBackground

Arka plan Fırçası.

```
HBRUSH m_hbrBackground;
```

## <a name="ccomcompositecontrolm_hwndfocus"></a><a name="m_hwndfocus"></a> CComCompositeControl:: m_hWndFocus

Şu anda odaklanmış pencerenin tutamacı.

```
HWND m_hWndFocus;
```

## <a name="ccomcompositecontrolsetbackgroundcolorfromambient"></a><a name="setbackgroundcolorfromambient"></a> CComCompositeControl:: SetBackgroundColorFromAmbient

Kapsayıcının arka plan rengini kullanarak bileşik denetimin arka plan rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Bileşik denetim temelleri](../../atl/atl-composite-control-fundamentals.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
