---
description: 'Daha fazla bilgi edinin: CWaitCursor sınıfı'
title: CWaitCursor sınıfı
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
ms.openlocfilehash: f9552dcd6f5304c96d550e153870f69d78d932ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318474"
---
# <a name="cwaitcursor-class"></a>CWaitCursor sınıfı

Uzun bir işlem gerçekleştirirken genellikle kum saati olarak görünen Bekleme imlecini göstermek için tek satırlık bir yol sağlar.

## <a name="syntax"></a>Syntax

```
class CWaitCursor
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWaitCursor:: CWaitCursor](#cwaitcursor)|Bir `CWaitCursor` nesnesi oluşturur ve Bekleme imlecini görüntüler.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWaitCursor:: restore](#restore)|Bekleme imlecini değiştirildikten sonra geri yükler.|

## <a name="remarks"></a>Açıklamalar

`CWaitCursor` taban sınıfına sahip değildir.

İyi Windows programlama uygulamaları, dikkat çekici bir süre alan bir işlem gerçekleştirirken bir bekleme imleci görüntülemenizi gerektirir.

Bekleme imlecini göstermek için, `CWaitCursor` uzun işlem gerçekleştiren koddan önce bir değişken tanımlamanız yeterlidir. Nesnenin oluşturucusu, bekleme imlecinin görüntülenmesini otomatik olarak sağlar.

Nesne kapsam dışına geçtiğinde ( `CWaitCursor` nesnenin bildirildiği bloğun sonunda), yok edicisi imleci önceki imleç olarak ayarlar. Diğer bir deyişle, nesne gerekli temizleme işlemini otomatik olarak gerçekleştirir.

> [!NOTE]
> Oluşturucularının ve yok edicilerin çalışma biçimi nedeniyle, `CWaitCursor` nesneler her zaman yerel değişkenler olarak (genel değişkenler olarak bildirilmemiş veya ile ayrılılar) olarak bildirilmez **`new`** .

Bir ileti kutusu veya iletişim kutusu görüntüleme gibi imleç değiştirilmesine neden olabilecek bir işlem gerçekleştirirseniz, Bekleme imlecini geri yüklemek için [restore](#restore) member işlevini çağırın. `Restore`Bekleme imleci Şu anda görüntülenirken bile çağrı yapmak normaldir.

Bekleme imlecini görüntülemenin bir başka yolu da [CCmdTarget:: BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget:: EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)ve belki [CCmdTarget:: RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)birleşimini kullanmaktır. Ancak, `CWaitCursor` uzun bir işlem yaptığınızda imleci önceki imlece ayarlamanız gerekmediğinden daha kolay bir şekilde kullanılır.

> [!NOTE]
> MFC, [CWinApp::D owaitcursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) sanal işlevini kullanarak imleci ayarlar ve geri yükler. Özel davranış sağlamak için bu işlevi geçersiz kılabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CWaitCursor`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

## <a name="cwaitcursorcwaitcursor"></a><a name="cwaitcursor"></a> CWaitCursor:: CWaitCursor

Bekleme imleci göstermek için, `CWaitCursor` uzun işlem gerçekleştiren koddan önce bir nesne bildirmeniz yeterlidir.

```
CWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, bekleme imlecinin görüntülenmesine otomatik olarak neden olur.

Nesne kapsam dışına geçtiğinde ( `CWaitCursor` nesnenin bildirildiği bloğun sonunda), yok edicisi imleci önceki imleç olarak ayarlar. Diğer bir deyişle, nesne gerekli temizleme işlemini otomatik olarak gerçekleştirir.

Yalnızca işlevinizin bir kısmında Bekleme imlecini etkin hale getirmek için, yok edicinin bloğun sonunda (işlevin sonundan önce olabilir) çağrıldığı Gerçektan yararlanabilirsiniz. Bu teknik aşağıdaki ikinci örnekte gösterilmiştir.

> [!NOTE]
> Oluşturucularının ve yıkıcılarının nasıl çalıştığı, `CWaitCursor` nesneler her zaman yerel değişkenler olarak (genel değişkenler olarak bildirilmemiş veya ile ayrıldıkları için) **`new`** .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

## <a name="cwaitcursorrestore"></a><a name="restore"></a> CWaitCursor:: restore

Bekleme imlecini geri yüklemek için, bir ileti kutusu veya iletişim kutusu görüntüleme gibi bir işlem gerçekleştirdikten sonra bu işlevi çağırın, bu durum, Bekleme imlecini başka bir imlece değiştirebilir.

```cpp
void Restore();
```

### <a name="remarks"></a>Açıklamalar

`Restore`Bekleme imleci Şu anda görüntülenirken bile çağrı yapmak daha iyidir.

Bekleme imlecini, nesnenin bildirildiği sunucudan farklı bir işlevde geri yüklemeniz gerekiyorsa `CWaitCursor` [CCmdTarget:: RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)öğesini çağırabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget:: BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget:: EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget:: RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::D oWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[Nasıl yapılır: bir Microsoft Foundation Class uygulamasında fare Imlecini değiştirme](https://go.microsoft.com/fwlink/p/?linkid=128044)
