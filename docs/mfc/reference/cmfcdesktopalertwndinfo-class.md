---
title: Cmfcdesktopalertwndınfo sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: d815abbd48e1744900853fcf81dc05b6af62788c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509076"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>Cmfcdesktopalertwndınfo sınıfı

`CMFCDesktopAlertWndInfo` Sınıfı ile kullanılır [CMFCDesktopAlertWnd sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md). Masaüstü uyarı penceresi açıldığında görüntülenen denetimleri belirtir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Görüntülenecek simge için bir tanıtıcı.|
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Bir bağlantıda bir Masaüstü Uyarısı açılır penceresi ile ilişkili komut kimliği.|
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Masaüstü Uyarısı açılır penceresi üzerinde görüntülenen metin.|
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Bağlantı üzerinde Masaüstü Uyarısı açılır penceresi görüntülenir.|

## <a name="remarks"></a>Açıklamalar

`CMFCDesktopAlertWndInfo` Sınıfı geçirildiğinde [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Masaüstü Uyarısı açılır penceresi varsayılan iletişim kutusunda görüntülenen öğeler belirtmek için yöntemi. Varsayılan iletişim üç öğe içerebilir:

- Çağırarak ayarlanmış bir simge [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).

- Bir etiket veya çağırarak ayarlanan kısa mesaj [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).

- Çağırarak ayarlanmış bir bağlantı [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Bağlantıya tıklandığında çalıştırılan komut ayarlamak için çağrı [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).

Varsayılan iletişim yeterli değilse, özel bir iletişim kutusu oluşturun ve geçirin [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Bu sınıf kullanmak yerine yöntemi. Daha fazla bilgi için [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli üyeleri kullanılacak gösterilmiştir `CMFCDesktopAlertWndInfo` sınıfı. Örnek tanıtıcı gösterilen simge Masaüstü Uyarısı açılır penceresi, Masaüstü Uyarısı açılır penceresi üzerinde görüntülenen bağlantıyı ve bağlantı Masaüstü Uyarısı açılır penceresi ile ilişkili komut Kimliğini görüntülenen metni ayarlama işlemini gösterir. Bu örneğin parçasıdır [Masaüstü uyarı gösterim örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cmfcdesktopalertwndınfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxDesktopAlertDialog.h

##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator =

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>Parametreler

[in] *src*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="m_hicon"></a>  CMFCDesktopAlertWndInfo::m_hIcon

Görüntülenecek simge için bir tanıtıcı.

```
HICON m_hIcon;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID

Bir bağlantıda bir Masaüstü Uyarısı açılır penceresi ile ilişkili komut kimliği.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>Açıklamalar

Komut kimliği, kullanıcı tarafından belirtilen bağlantıya tıkladığında açılan pencere sahibine gönderilir [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).

##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText

Masaüstü Uyarısı açılır penceresi üzerinde görüntülenen metin.

```
CString m_strText;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL

Bağlantı üzerinde Masaüstü Uyarısı açılır penceresi görüntülenir.

```
CString m_strURL;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı bağlantıyı tıklattığında, olan komut [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) komut kimliği açılır pencerede sahibine gönderilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog Sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
