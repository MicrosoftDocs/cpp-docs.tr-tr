---
description: 'Daha fazla bilgi edinin: Cmfcdesktopalertwnınfo sınıfı'
title: Cmfcdesktopalertwnınfo sınıfı
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
ms.openlocfilehash: 1c23e5b890e892df9bccce51542f2d36b3d6f7d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250692"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>Cmfcdesktopalertwnınfo sınıfı

`CMFCDesktopAlertWndInfo`Sınıfı, [CMFCDesktopAlertWnd sınıfıyla](../../mfc/reference/cmfcdesktopalertwnd-class.md)birlikte kullanılır. Masaüstü Uyarısı penceresi açılıp görüntülenmediğinde görüntülenen denetimleri belirtir.

## <a name="syntax"></a>Syntax

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
|[Cmfcdesktopalertwnınfo:: operator =](#operator_eq)||

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcdesktopalertwnınfo:: m_hIcon](#m_hicon)|Görüntülenen simgeye yönelik bir tanıtıcı.|
|[Cmfcdesktopalertwnınfo:: m_nURLCmdID](#m_nurlcmdid)|Masaüstü Uyarısı penceresindeki bir bağlantıyla ilişkili komut KIMLIĞI.|
|[Cmfcdesktopalertwnınfo:: m_strText](#m_strtext)|Masaüstü Uyarısı penceresinde görüntülenen metin.|
|[Cmfcdesktopalertwnınfo:: m_strURL](#m_strurl)|Masaüstü Uyarısı penceresinde görüntülenen bağlantı.|

## <a name="remarks"></a>Açıklamalar

`CMFCDesktopAlertWndInfo`Sınıfı, masaüstü uyarı penceresinin varsayılan iletişim kutusunda görüntülenen öğeleri belirtmek Için [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) yöntemine geçirilir. Varsayılan iletişim kutusunda üç öğe bulunabilir:

- [Cmfcdesktopalertwnınfo:: m_hIcon](#m_hicon)çağırarak ayarlanan bir simge.

- [Cmfcdesktopalertwnınfo:: m_strText](#m_strtext)çağırarak ayarlanan bir etiket veya kısa mesaj.

- [Cmfcdesktopalertwnınfo:: m_strURL](#m_strurl)çağırarak ayarlanan bir bağlantı. Bağlantıya tıklandığında yürütülen komutu ayarlamak için [Cmfcdesktopalertwnınfo:: m_nURLCmdID](#m_nurlcmdid)çağırın.

Varsayılan iletişim kutusu yeterli değilse, özel bir iletişim kutusu oluşturabilir ve bu sınıfı kullanmak yerine [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) yöntemine geçirebilirsiniz. Daha fazla bilgi için bkz. [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli üyelerin nasıl kullanıldığını gösterir `CMFCDesktopAlertWndInfo` . Örnek, işleyicinin görüntülenen simgeye, masaüstü uyarı penceresinde görüntülenen metne, Masaüstü Uyarısı penceresinde görüntülenen bağlantıya ve Masaüstü Uyarısı penceresindeki bir bağlantıyla ilişkili komut KIMLIĞINE nasıl ayarlanacağını gösterir... Bu örnek, [Masaüstü Uyarısı tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDesktopAlertDialog. h

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a> Cmfcdesktopalertwnınfo:: operator =

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>Parametreler

'ndaki *src*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a> Cmfcdesktopalertwnınfo:: m_hIcon

Görüntülenen simgeye yönelik bir tanıtıcı.

```
HICON m_hIcon;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a> Cmfcdesktopalertwnınfo:: m_nURLCmdID

Masaüstü Uyarısı penceresindeki bir bağlantıyla ilişkili komut KIMLIĞI.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>Açıklamalar

Komut KIMLIĞI, Kullanıcı [Cmfcdesktopalertwnınfo:: m_strURL](#m_strurl)tarafından belirtilen bağlantıyı tıklattığında açılan pencerenin sahibine gönderilir.

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a> Cmfcdesktopalertwnınfo:: m_strText

Masaüstü Uyarısı penceresinde görüntülenen metin.

```
CString m_strText;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a> Cmfcdesktopalertwnınfo:: m_strURL

Masaüstü Uyarısı penceresinde görüntülenen bağlantı.

```
CString m_strURL;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı bağlantıya tıkladığında, [Cmfcdesktopalertwnınfo:: m_nURLCmdID](#m_nurlcmdid) komut kimliği olan komut açılır pencerenin sahibine gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
