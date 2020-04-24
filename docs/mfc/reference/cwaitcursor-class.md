---
title: CWaitCursor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
ms.openlocfilehash: aaa60e26d0a9bf99076f29124097b0629ce6f5d0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754321"
---
# <a name="cwaitcursor-class"></a>CWaitCursor Sınıfı

Uzun bir işlem yaparken genellikle kum saati olarak görüntülenen bekleme imlecini göstermek için tek satırlık bir yol sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CWaitCursor
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Bir `CWaitCursor` nesne oluşturuyor ve bekleme imlecini görüntüler.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWaitCursor::Geri Yükleme](#restore)|Değiştirildikten sonra bekleme imlecini geri yükler.|

## <a name="remarks"></a>Açıklamalar

`CWaitCursor`taban sınıfa sahip değildir.

İyi Windows programlama uygulamaları, fark edilebilir bir süre alan bir işlem gerçekleştirirken bir bekleme imleci görüntülemenizi gerektirir.

Bekleme imlecini görüntülemek için, uzun `CWaitCursor` işlemi gerçekleştiren koddan önce bir değişken tanımlamaniz kaldı. Nesnenin oluşturucusu bekleme imlecinin otomatik olarak görüntülenmesine neden olur.

Nesne kapsam dışına çıktığında `CWaitCursor` (nesnenin bildirildiği bloğun sonunda), yıkıcısı imleci önceki imlecin için ayarlar. Başka bir deyişle, nesne gerekli temizlemeyi otomatik olarak gerçekleştirir.

> [!NOTE]
> Yapı yapıcıları ve yıkıcıları nasıl çalıştıklarından dolayı, `CWaitCursor` nesneler her zaman yerel değişkenler olarak bildirilir — hiçbir zaman küresel değişken olarak beyan edilmemişlerdir ve **yeni**değişkenlerle tahsis edilirler.

İleti kutusu veya iletişim kutusu görüntülemek gibi imlecin değiştirilmesine neden olabilecek bir işlem yaparsanız, bekle imlecini geri yüklemek için üye işlevi [geri yükleyin.](#restore) Bekleme imleci `Restore` şu anda görüntülendiğinde bile arama nın sakıncası yoktur.

Bekleme imlecini görüntülemenin başka bir yolu [ccmdTarget kombinasyonunu kullanmaktır::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), ve belki de [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Ancak, `CWaitCursor` uzun işlem bittiğinde imleci önceki imlecin olarak ayarlamanız gerekmediği için kullanımı daha kolaydır.

> [!NOTE]
> MFC, [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) sanal işlevini kullanarak imleci ayarlar ve geri getirir. Özel davranış sağlamak için bu işlevi geçersiz kılabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CWaitCursor`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

## <a name="cwaitcursorcwaitcursor"></a><a name="cwaitcursor"></a>CWaitCursor::CWaitCursor

Bekleme imlecini görüntülemek için, uzun `CWaitCursor` işlemi gerçekleştiren koddan önce bir nesne bildirmeniz.

```
CWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu otomatik olarak bekleme imlecinin görüntülenmesine neden olur.

Nesne kapsam dışına çıktığında `CWaitCursor` (nesnenin bildirildiği bloğun sonunda), yıkıcısı imleci önceki imlecin için ayarlar. Başka bir deyişle, nesne gerekli temizlemeyi otomatik olarak gerçekleştirir.

Bekleme imlecini işlevinizin yalnızca bir bölümünde etkin hale getirmek için, yıkıcının bloğun sonunda (işlevin bitiminden önce olabilir) çağrılması durumundan yararlanabilirsiniz. Bu teknik aşağıdaki ikinci örnekte gösterilmiştir.

> [!NOTE]
> Yapı yapıcıları ve yıkıcıları nasıl çalıştıklarından dolayı, `CWaitCursor` nesneler her zaman yerel değişkenler olarak bildirilir — hiçbir zaman küresel değişken olarak beyan edilmemişlerdir, ne de **yeni**değişkenlerle tahsis edilirler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

## <a name="cwaitcursorrestore"></a><a name="restore"></a>CWaitCursor::Geri Yükleme

Bekleme imlecini geri yüklemek için, bekleme imlecini başka bir imleçle değiştirebilecek ileti kutusu veya iletişim kutusu görüntülemek gibi bir işlem yaptıktan sonra bu işlevi arayın.

```cpp
void Restore();
```

### <a name="remarks"></a>Açıklamalar

Bekleme imleci `Restore` şu anda görüntülendiğinde bile arama nın sakıncası yoktur.

`CWaitCursor` Nesnenin beyan edildiği işlev dışında bir işlevde bekleme imlecini geri yüklemeniz gerekiyorsa, [CCmdTarget::RestoreWaitCursor'u](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)arayabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[Nasıl Yaparım: Microsoft Hazırlık Sınıfı Uygulamasında Fare İmlörünü Değiştirme](https://go.microsoft.com/fwlink/p/?linkid=128044)
