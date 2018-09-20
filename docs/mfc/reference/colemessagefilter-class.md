---
title: COleMessageFilter sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
dev_langs:
- C++
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 585044a5da8ca3ce8b2650801558b19bf1d5ef59
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427803"
---
# <a name="colemessagefilter-class"></a>COleMessageFilter sınıfı

OLE uygulamalarının etkileşimi tarafından gereken eşzamanlılığı yönetir.

## <a name="syntax"></a>Sözdizimi

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|Oluşturur bir `COleMessageFilter` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Uygulama meşgul duruma geçer.|
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Adlı bir uygulama meşgul olduğunda görüntülenen iletişim kutusunda devre dışı bırakır ve sağlar.|
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Adlı bir uygulama yanıt vermediğinde görüntülenen iletişim kutusunda devre dışı bırakır ve sağlar.|
|[COleMessageFilter::EndBusyState](#endbusystate)|Uygulama meşgul durumu sonlandırır.|
|[COleMessageFilter::OnMessagePending](#onmessagepending)|OLE çağrısı devam ederken işlemek için framework tarafından çağırılır.|
|[COleMessageFilter::Register](#register)|İleti Filtresi OLE sistem DLL'lerini kaydeder.|
|[COleMessageFilter::Revoke](#revoke)|OLE sistem DLL'lerini ileti filtrenin kaydı iptal eder.|
|[COleMessageFilter::SetBusyReply](#setbusyreply)|OLE çağrısı meşgul uygulamanın yanıt belirler.|
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Uygulama yanıt OLE çağrısı ne kadar bekleyeceğini belirler.|
|[COleMessageFilter::SetRetryReply](#setretryreply)|Çağıran uygulamanın yanıt meşgul bir uygulamaya belirler.|

## <a name="remarks"></a>Açıklamalar

`COleMessageFilter` Sınıfı, görsel düzenleme sunucusu ve kapsayıcı uygulamaları, aynı zamanda OLE Otomasyon uygulamaları kullanışlıdır. Çağrıldığını sunucu uygulamaları için bu sınıf, böylece diğer kapsayıcı uygulamalardan gelen çağrıları iptal edildi veya daha sonra yeniden uygulamayı "meşgul" yapmak için kullanılabilir. Bu sınıf, çağrılan uygulama meşgul olduğunda çağıran bir uygulama tarafından gerçekleştirilecek eylemi belirlemek için de kullanılabilir.

Yaygın kullanım çağırmak bir sunucu uygulaması için olan [BeginBusyState](#beginbusystate) ve [EndBusyState](#endbusystate) ne zaman, bir belge veya diğer OLE erişilebilir nesne yok edileceği için tehlikeli olabilir. İçinde bu çağrıları yapılan [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) sırasında kullanıcı arabirimi güncelleştirmeleri.

Varsayılan olarak, bir `COleMessageFilter` nesne, uygulama başlatıldığında ayrılır. İle alınabilir [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

Bu gelişmiş bir sınıftır; nadiren ile doğrudan çalışmanız gerekiyor.

Daha fazla bilgi için bkz [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="beginbusystate"></a>  COleMessageFilter::BeginBusyState

Meşgul bir durum başlamak için bu işlevi çağırın.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>Açıklamalar

İle birlikte çalıştığını [EndBusyState](#endbusystate) uygulamanın meşgul durumu denetlemek için. İşlev [SetBusyReply](#setbusyreply) meşgul olduğunda, uygulamalar için uygulamanın yanıt belirler.

`BeginBusyState` Ve `EndBusyState` çağrıları artırmak ve sırasıyla uygulama meşgul olup olmadığını belirleyen bir sayaç azaltma. Örneğin, iki için çağırdığı `BeginBusyState` ve çağrı `EndBusyState` hala meşgul bir durum sonuçlanır. Bu çağrı için gerekli meşgul bir durum iptal etmek için `EndBusyState` aynı sayıda `BeginBusyState` çağrıldı.

Varsayılan olarak, çerçeve tarafından gerçekleştirilen boşta işleme sırasında meşgul duruma girer [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Uygulama bildirimleri ON_COMMANDUPDATEUI işlerken boşta işleme tamamlandıktan sonra gelen çağrıları daha sonra işlenir.

##  <a name="colemessagefilter"></a>  COleMessageFilter::COleMessageFilter

Oluşturur bir `COleMessageFilter` nesne.

```
COleMessageFilter();
```

##  <a name="enablebusydialog"></a>  COleMessageFilter::EnableBusyDialog

İleti bekleyen gecikme süresi dolduğunda görüntülenen meşgul iletişim kutusu devre dışı bırakır ve sağlar (bkz [SetRetryReply](#setretryreply)) bir OLE çağrısı sırasında.

```
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnableBusy*<br/>
"Meşgul" iletişim kutusu etkin mi yoksa devre dışı mı olduğunu belirtir.

##  <a name="enablenotrespondingdialog"></a>  COleMessageFilter::EnableNotRespondingDialog

Sağlar ve bir klavye veya fare mesajı bekleme durumundaysa görüntülenen "vermiyor" iletişim kutusunda, devre dışı bırakır sırasında bir OLE çağrısı ve çağrısı zaman aşımına uğradı.

```
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnableNotResponding*<br/>
"Vermiyor" iletişim kutusu etkin mi yoksa devre dışı mı olduğunu belirtir.

##  <a name="endbusystate"></a>  COleMessageFilter::EndBusyState

Meşgul bir durum sona erdirmek için bu işlevi çağırın.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>Açıklamalar

İle birlikte çalıştığını [BeginBusyState](#beginbusystate) uygulamanın meşgul durumu denetlemek için. İşlev [SetBusyReply](#setbusyreply) meşgul olduğunda, uygulamalar için uygulamanın yanıt belirler.

`BeginBusyState` Ve `EndBusyState` çağrıları artırmak ve sırasıyla uygulama meşgul olup olmadığını belirleyen bir sayaç azaltma. Örneğin, iki için çağırdığı `BeginBusyState` ve çağrı `EndBusyState` hala meşgul bir durum sonuçlanır. Bu çağrı için gerekli meşgul bir durum iptal etmek için `EndBusyState` aynı sayıda `BeginBusyState` çağrıldı.

Varsayılan olarak, çerçeve tarafından gerçekleştirilen boşta işleme sırasında meşgul duruma girer [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Uygulama bildirimleri on_update_command_uı işlerken boşta işleme tamamlandıktan sonra gelen çağrıları işlenir.

##  <a name="onmessagepending"></a>  COleMessageFilter::OnMessagePending

OLE çağrısı devam ederken işlemek için framework tarafından çağırılır.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
Bekleyen iletisi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağıran bir uygulama bir çağrı tamamlanması beklenirken framework çağırır `OnMessagePending` işaretçiyle bekleyen iletisi. Bir uzun süren bir çağrı sırasında penceresi güncelleştirmeleri gerçekleştirilmesi varsayılan olarak, çerçeve WM_PAINT iletileri gönderir.

Bir çağrı yoluyla, İleti Filtresi kaydetmelisiniz [kaydetme](#register) etkin olabilmesi için önce.

##  <a name="register"></a>  COleMessageFilter::Register

İleti Filtresi OLE sistem DLL'lerini kaydeder.

```
BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sistem DLL'lerini kayıtlı olduğu sürece bir ileti filtresi bir etkisi yoktur. Genellikle, uygulamanızın başlatma kodunu uygulama İleti Filtresi kaydeder. Program bir çağrı tarafından sonlandırılmadan önce uygulamanız tarafından kaydedilen diğer İleti Filtresi iptal edilip edilmeyeceğini [iptal](#revoke).

Varsayılan ileti filtre framework'ün otomatik olarak başlatma sırasında kayıtlı ve sonlandırma sırasında iptal edildi.

##  <a name="revoke"></a>  COleMessageFilter::Revoke

Bir çağrı tarafından gerçekleştirilen bir önceki kaydı iptal eder [kaydetme](#register).

```
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

İleti filtresini, program sonlandırılmadan önce iptal edilmesi gerekir.

Oluşturulur ve framework tarafından otomatik olarak kayıtlı, varsayılan ileti filtresi da otomatik olarak iptal edilir.

##  <a name="setbusyreply"></a>  COleMessageFilter::SetBusyReply

Bu işlevi uygulamanın "meşgul yanıtı." ayarlar

```
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>Parametreler

*nBusyReply*<br/>
Bir değer `SERVERCALL` COMPOBJ içinde tanımlanan sabit listesi. H Bunu, aşağıdaki değerlerden biri olabilir:

- SERVERCALL_ISHANDLED uygulama çağrıları kabul edebilir, ancak belirli bir çağrı işlenirken başarısız olabilir.

- SERVERCALL_REJECTED uygulamanın büyük olasılıkla hiçbir zaman bir çağrısı işleme mümkün olacaktır.

- SERVERCALL_RETRYLATER uygulama geçici olarak bunu bir çağrı işlenemiyor bir durumda.

### <a name="remarks"></a>Açıklamalar

[BeginBusyState](#beginbusystate) ve [EndBusyState](#endbusystate) işlevleri uygulamanın meşgul durumu denetleme.

Ne zaman bir uygulama yapılan bir çağrıyla meşgul `BeginBusyState`, son ayarı tarafından belirlenen bir değerle OLE sistem DLL'lerini çağrısına yanıt `SetBusyReply`. Çağıran uygulamanın bu meşgul yanıtı hangi eylemin yapılacağını belirlemek için kullanır.

Varsayılan olarak, meşgul yanıtı SERVERCALL_RETRYLATER ' dir. Bu yanıt, çağıran uygulama çağrı mümkün olan en kısa sürede yeniden denemek neden olur.

##  <a name="setmessagependingdelay"></a>  COleMessageFilter::SetMessagePendingDelay

Çağıran uygulamanın yanıt çağrılan uygulamadaki başka eyleme girişmeden önce ne kadar bekleyeceğini belirler.

```
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>Parametreler

*nTimeout*<br/>
İleti bekleyen gecikme süresini milisaniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev uyumlu bir şekilde çalışır [SetRetryReply](#setretryreply).

##  <a name="setretryreply"></a>  COleMessageFilter::SetRetryReply

Adlı bir uygulamadan meşgul yanıtı aldığında çağıran uygulama eylemi belirler.

```
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>Parametreler

*nRetryReply*<br/>
Yeniden denemeler arasındaki milisaniye sayısı.

### <a name="remarks"></a>Açıklamalar

Adlı bir uygulama meşgul olduğunu gösteriyorsa, çağıran uygulama sunucusu artık meşgul hemen yeniden deneyin ya da belirtilen bir süre sonra yeniden deneyin kadar bekleyin karar verebilirsiniz. Çağrı tamamen iptal etmek de karar verebilirsiniz.

Çağıranın yanıt işlevleri tarafından denetlenir `SetRetryReply` ve [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply` çağıran uygulamanın belirli bir çağrı için yeniden denemeler arasında ne kadar beklemesi gerektiğini belirler. `SetMessagePendingDelay` çağıran uygulama sunucusundan bir yanıt için başka bir eylemde bulunmadan önce bekleyeceği süreyi belirler.

Genellikle, Varsayılanları kabul edilir ve değiştirilmesi gerekmez. Çerçeve çağrı yeniden deneme her *nRetryReply* iletisi bekleyen gecikme süresi doldu veya çağrı geçtiği kadar milisaniye. Bir değer için 0 *nRetryReply* hemen yeniden ve - 1 iptal çağrısı belirtir.

Ne zaman ileti bekleyen gecikme süresi, "meşgul iletişim kutusu" OLE (bkz [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) kullanıcı iptal etme veya çağrıyı yeniden denemesi seçebilmeniz görüntülenir. Çağrı [EnableBusyDialog](#enablebusydialog) etkinleştirme veya bu iletişim kutusunu devre dışı.

Klavye veya fare bir ileti olduğunda bekleyen bir çağrı ve çağrı sırasında zaman aşımına uğradı (ileti bekleyen gecikme aşıldı), "vermiyor" iletişim kutusu görüntülenir. Çağrı [EnableNotRespondingDialog](#enablenotrespondingdialog) etkinleştirme veya bu iletişim kutusunu devre dışı. Genellikle bu durumu, bir sorun oluştu ve kullanıcı sabırsız alma gösterir.

İletişim kutularını devre dışı bırakıldığında geçerli "yeniden deneme yanıt" her zaman çağrılar yoğun uygulamalar için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
