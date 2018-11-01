---
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
ms.openlocfilehash: 10daa8c5af84b17d70cc18c9407686d4698e98a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533633"
---
# <a name="cwaitcursor-class"></a>CWaitCursor sınıfı

Uzun bir işlem yaparken, genellikle bir kum saati görüntülenen bekleme imlecini göstermek için bir yol sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CWaitCursor
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Oluşturur bir `CWaitCursor` nesne ve bekleme imleci görüntüler.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWaitCursor::Restore](#restore)|Bekleme imleci değiştirilmiş sonra geri yükler.|

## <a name="remarks"></a>Açıklamalar

`CWaitCursor` bir temel sınıfa sahip değil.

İyi Windows uygulamalarını programlama belirgin bir süre sürer bir işlemi gerçekleştiriyorsunuz her bekleme imlecini görüntüleme gerektirir.

Bekleme imlecini görüntülenecek tanımlamak bir `CWaitCursor` kilitlemekten gerçekleştiren kod önce değişken. Nesnenin oluşturucusunun otomatik olarak görüntülenecek bekleme imlecini neden olur.

Nesne kapsam dışına gittiğinde (bloğunda sonunda `CWaitCursor` nesne bildirilir), yok edici imleci önceki imleci ayarlar. Diğer bir deyişle, nesne gerekli temizleme otomatik olarak gerçekleştirir.

> [!NOTE]
>  Kendi oluşturucularının ve yıkıcılarının nasıl çalıştığını, nedeniyle `CWaitCursor` nesneler her zaman yerel değişkenler olarak bildirilen — ne de ile ayrılmış genel değişkenler hiçbir zaman bildirildikleri **yeni**.

İmleci görüntüleme gibi bir ileti kutusu veya iletişim kutusu, çağrı değiştirilecek neden bir işlem gerçekleştiriyorsanız [geri](#restore) bekleme imleci geri yüklemek için üye işlevi. Çağırmak uygundur `Restore` bile zaman bekleme imlecini şu anda görüntülenir.

Bekleme imlecini görüntülemek için başka bir bileşimini kullanmaktır [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)belki [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Ancak, `CWaitCursor` kilitlemekten ile işiniz bittiğinde, imleci önceki imleci ayarlamanız gerekmez çünkü kullanmak daha kolaydır.

> [!NOTE]
>  MFC imleç kullanarak geri yükler ve ayarlar [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) sanal işlev. Özel davranış sağlamak için bu işlevi geçersiz kılabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CWaitCursor`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

##  <a name="cwaitcursor"></a>  CWaitCursor::CWaitCursor

Bekleme imlecini görüntülemek için yalnızca bildirme bir `CWaitCursor` kilitlemekten gerçekleştiren kod önce nesne.

```
CWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu otomatik olarak görüntülenecek bekleme imlecini neden olur.

Nesne kapsam dışına gittiğinde (bloğunda sonunda `CWaitCursor` nesne bildirilir), yok edici imleci önceki imleci ayarlar. Diğer bir deyişle, nesne gerekli temizleme otomatik olarak gerçekleştirir.

Yok edici (Bu işlevin sonuna önce olabilir) bloğunun sonunda bekleme imleci yalnızca işlevinizi bir parçası etkin hale getirmek için çağrıldığını olayının yararlanabilirsiniz. Bu teknik, aşağıdaki ikinci örnekte gösterilir.

> [!NOTE]
>  Kendi oluşturucularının ve yıkıcılarının nasıl çalıştığını, nedeniyle `CWaitCursor` nesneler her zaman yerel değişkenler olarak bildirilen — asla genel değişkenleri olarak bildirilirler ya da ile ayrılan **yeni**.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

##  <a name="restore"></a>  CWaitCursor::Restore

Bekleme imleci geri yüklemek için bir ileti kutusu ya da bekleme imleci için başka bir imleç değişebilir iletişim kutusunda, görüntüleme gibi bir işlem gerçekleştirildikten sonra bu işlevi çağırın.

```
void Restore();
```

### <a name="remarks"></a>Açıklamalar

Çağırmak için Tamam olduğunu `Restore` bile zaman bekleme imleci şu anda görüntülenir.

Bekleme imleci dışında olan bir işlevde sırada geri yüklemeniz gerekirse `CWaitCursor` nesne bildirildiğinde, çağırabilirsiniz [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[Nasıl Yaparım: bir Microsoft Foundation sınıf uygulaması fare imlecini değişiklik olur mu](http://go.microsoft.com/fwlink/p/?linkid=128044)

