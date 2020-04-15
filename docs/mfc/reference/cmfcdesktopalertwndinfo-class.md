---
title: CMFCDesktopAlertWndInfo Sınıfı
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
ms.openlocfilehash: f51c1b75e0c096a34b190e36e097aaca4109b5f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367580"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo Sınıfı

Sınıf `CMFCDesktopAlertWndInfo` [CMFCDesktopAlertWnd Sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)ile kullanılır. Masaüstü uyarı penceresi açılırsa görüntülenen denetimleri belirtir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::operatör=](#operator_eq)||

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Görüntülenen simgenin tutamacı.|
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Masaüstü uyarı penceresindeki bir bağlantıyla ilişkili komut kimliği.|
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Masaüstü uyarı penceresinde görüntülenen metin.|
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Masaüstü uyarı penceresinde görüntülenen bağlantı.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CMFCDesktopAlertWndInfo` [CMFCDesktopAlertWnd geçirilir::Masaüstü](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) uyarı penceresinin varsayılan iletişim kutusunda görüntülenen öğeleri belirtmek için yöntem oluşturma. Varsayılan iletişim kutusu üç öğe içerebilir:

- [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)numaralı arayarak ayarlanan bir simge.

- [CMFCDesktopAlertWndInfo::m_strText'](#m_strtext)yi arayarak ayarlanan bir etiket veya kısa mesaj.

- [CMFCDesktopAlertWndInfo](#m_strurl)arayarak ayarlanan bir bağlantı::m_strURL . Bağlantı tıklandığında çalıştırılan komutu ayarlamak için [CMFCDesktopAlertWndInfo:m_nURLCmdID'](#m_nurlcmdid)ı arayın.

Varsayılan iletişim kutusu yeterli değilse, özel bir iletişim kutusu oluşturabilir ve [cmfcDesktopAlertWnd'e geçirebilirsiniz::Bu](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) sınıfı kullanmak yerine yöntem oluştur. Daha fazla bilgi için [CMFCDesktopAlertDialog Class'a](../../mfc/reference/cmfcdesktopalertdialog-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıftaki çeşitli üyelerin `CMFCDesktopAlertWndInfo` nasıl kullanılacağını göstermektedir. Örnek, tanıtıcının görüntülenen simgeye nasıl ayarleneceğini, masaüstü uyarı penceresinde görüntülenen metni, masaüstü uyarı penceresinde görüntülenen bağlantıyı ve masaüstü uyarı penceresindeki bir bağlantıyla ilişkili komut kimliğini gösterir. Bu örnek, [Desktop Alert Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDesktopAlertDialog.h

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a>CMFCDesktopAlertWndInfo::operatör=

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>Parametreler

[içinde] *src*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a>CMFCDesktopAlertWndInfo::m_hIcon

Görüntülenen simgenin tutamacı.

```
HICON m_hIcon;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a>CMFCDesktopAlertWndInfo::m_nURLCmdID

Masaüstü uyarı penceresindeki bir bağlantıyla ilişkili komut kimliği.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>Açıklamalar

Komut kimliği, kullanıcı [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)tarafından belirtilen bağlantıyı tıklattığında açılır pencerenin sahibine gönderilir.

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText

Masaüstü uyarı penceresinde görüntülenen metin.

```
CString m_strText;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a>CMFCDesktopAlertWndInfo::m_strURL

Masaüstü uyarı penceresinde görüntülenen bağlantı.

```
CString m_strURL;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı bağlantıyı tıklattığında, [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) komut kimliği açılır pencerenin sahibine gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd::Oluştur](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog Sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
