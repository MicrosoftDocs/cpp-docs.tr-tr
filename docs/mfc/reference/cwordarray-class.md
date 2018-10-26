---
title: CWordArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 798e3d0a7cc8d8573c03f9859b722c95b8c640af
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070263"
---
# <a name="cwordarray-class"></a>CWordArray sınıfı

16 bit sözcük dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CWordArray : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CWordArray` sınıfın üye işlevleri için benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CObArray` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir [CObject](../../mfc/reference/cobject-class.md) işaretçi bir işlev parametre veya dönüş değeri olarak alternatif bir sözcük.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, için çevirir

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; dizi gerekirse büyür.|
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Diziyi başka diziye ekler; dizi gerekirse büyür.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Diziyi başka diziye kopyalar; dizi gerekirse büyür.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içinde öğe işaretçisi için geçici bir başvuru döndürür.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirtilen dizindeki değeri döndürür.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizide öğelere erişim sağlar. NULL olabilir.|
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizinini döndürür.|
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.|
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizi boş olup olmadığını belirler.|
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizisinden tüm öğeleri kaldırır.|
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki öğeyi kaldırır.|
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirtilen dizin için değeri ayarlar; dizi büyümesine izin verilmiyor.|
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirtilen dizin için değeri ayarlar; dizi gerekirse büyür.|
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizinin içinde yer alması için öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CWordArray` içerir [ımplement_serıal](run-time-object-model-services.md#implement_serial) seri hale getirme ve alt öğeleri dökme desteklemek için makrosu. Sözcük dizisi veya aşırı yüklenmiş bir ekleme operatörü ile birlikte bir arşiv depolanıyorsa [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) üye işlevi, her öğe olan, sırayla, serileştirilmiş.

> [!NOTE]
>  Bir dizi kullanmadan önce kullanmayı `SetSize` boyutuna kurmak ve kendisi için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.

Bir dizideki tek tek öğelerin dökümü gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

Kullanma hakkında daha fazla bilgi için `CWordArray`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

##  <a name="icommandsource_interface"></a>  ICommandSource arabirimi

Bir kullanıcı denetimine komut kaynak nesneden gönderilen komutları yönetir.

```
interface class ICommandSource
```

### <a name="remarks"></a>Açıklamalar

MFC görünümü, bir kullanıcı denetiminde barındırdığınızda [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md) yollar komutları ve güncelleştirme komut UI iletilerini MFC komutlarını (örneğin, çerçeve menüsü ögeleri ve araç çubuğu düğmeleri) işlemelerine izin vermek için kullanıcı denetimi için. Uygulayarak, kullanıcı denetimine bir başvuru size `ICommandSource` nesne.

Bkz [nasıl yapılır: Windows Forms denetimi için komut yönlendirme ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler

Bir komut işleyici, bir komut kaynak nesnesine ekler.

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

*cmdHandler*<br/>
Komut işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem komut işleyici ekler *cmdHandler* komut kaynak nesnesine ve işleyiciye eşler *cmdID*.

Bkz [nasıl yapılır: Windows Forms denetimi için komut yönlendirme ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `AddCommandHandler`.

##  <a name="addcommandrangehandler"></a>  ICommandSource::AddCommandRangeHandler

Komut işleyicileri grubu, bir komut kaynak nesnesine ekler.

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.

*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.

*cmdHandler*<br/>
Komutlar eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir tek ileti işleyici komut kimlikleri bir aralıkta eşler ve komut kaynak nesnesine ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.

##  <a name="addcommandrangeuihandler"></a>  ICommandSource::AddCommandRangeUIHandler

Bir grup kullanıcı arabirimi komut ileti işleyicileri, bir komut kaynak nesnesine ekler.

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.

*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.

*cmdHandler*<br/>
Komutlar eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir tek bir kullanıcı arabirimi komut ileti işleyicisi komut kimlikleri bir aralıkta eşler ve komut kaynak nesnesine ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.

##  <a name="addcommanduihandler"></a>  ICommandSource::AddCommandUIHandler

Bir kullanıcı arabirimi komut ileti işleyicisi komut kaynak nesnesine ekler.

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

*cmdUIHandler*<br/>
Kullanıcı arabirimi komut ileti işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem kullanıcı arabirimi komut ileti işleyicisi ekler *cmdHandler* komut kaynak nesnesine ve işleyiciye eşler *cmdID*.

##  <a name="postcommand"></a>  ICommandSource::PostCommand

İşlenmesi için beklemenize gerek kalmadan bir ileti gönderir.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*Komutu*<br/>
Yayımlanacak ileti komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından belirtilen kimliği eşlenen bir ileti zaman uyumsuz olarak gönderir. *komut*. Çağrı [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) karşılık gelen penceresi iletiyi işlemek beklemenize gerek kalmadan pencere ileti kuyruğu ve sonra geri ileti yerleştirmek için.

##  <a name="removecommandhandler"></a>  ICommandSource::RemoveCommandHandler

Bir komut işleyici, bir komut kaynak nesneden kaldırır.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem eşlenmiş komut işleyici kaldırır *cmdID* komut kaynak nesnesi.

##  <a name="removecommandrangehandler"></a>  ICommandSource::RemoveCommandRangeHandler

Bir grup komut işleyicileri komut kaynak nesnesinden kaldırır.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.

*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir grup tarafından komut kimlikleri belirtilen eşlenen ileti işleyicilerini kaldırır *cmdIDMin* ve *cmdIDMax*, komut kaynak nesnesi.

##  <a name="removecommandrangeuihandler"></a>  ICommandSource::RemoveCommandRangeUIHandler

Bir grup kullanıcı arabirimi komut ileti işleyicileri komut kaynak nesnesinden kaldırır.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.

*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir grup tarafından komut kimlikleri belirtilen eşlenen kullanıcı arabirimi komut ileti işleyicilerini kaldırır *cmdIDMin* ve *cmdIDMax*, komut kaynak nesnesi.

##  <a name="removecommanduihandler"></a>  ICommandSource::RemoveCommandUIHandler

Bir kullanıcı arabirimi komut ileti işleyicisi komut kaynak nesnesinden kaldırır.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem eşlenen kullanıcı arabirimi komut ileti işleyicisini kaldırır *cmdID* komut kaynak nesnesi.

##  <a name="sendcommand"></a>  ICommandSource::SendCommand

Bir ileti gönderir ve döndürmeden önce işlenecek bekler.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*Komutu*<br/>
Gönderilecek iletinin komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, zaman uyumlu olarak tarafından belirtilen kimliği eşlenen bir ileti gönderir *komut*. Çağrı [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) Bu pencere yordamını döndürmeden önce iletiyi işleyene kadar pencere ileti kuyruğu ve bekler ileti yerleştirmek için.

##  <a name="icommandtarget_interface"></a>  ICommandTarget arabirimi

Bir kullanıcı denetimi komutları komut kaynak nesneden almak için bir arabirim sağlar.

```
interface class ICommandTarget
```

### <a name="remarks"></a>Açıklamalar

MFC görünümü, bir kullanıcı denetiminde barındırdığınızda [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yollar komutları ve güncelleştirme komut UI iletilerini MFC komutlarını (örneğin, çerçeve menüsü ögeleri ve araç çubuğu düğmeleri) işlemelerine izin vermek için kullanıcı denetimi için. Uygulayarak `ICommandTarget`, kullanıcı denetimi nesnesine bir başvuru sağlar.

Bkz [nasıl yapılır: Windows Forms denetimi için komut yönlendirme ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="initialize"></a>  ICommandTarget::Initialize'ı

Komut hedef nesnesi başlatır.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parametreler

*cmdSource*<br/>
Komut kaynak nesnesine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

MFC görünümü, bir kullanıcı denetiminde barındırdığınızda [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yollar komutları ve güncelleştirme komut UI iletilerini MFC komutlarını işlemelerine izin vermek için kullanıcı denetimi için.

Bu yöntem, komut hedef nesnesini başlatır ve belirtilen komut kaynak nesnesi ile ilişkilendirir *cmdSource*. Kullanıcı denetimi sınıf uygulamasında çağrılmalıdır. Başlatma sırasında komut işleyicileri komut kaynak nesnesi ile çağırarak kayıt [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) içinde `Initialize` uygulaması. Bkz [nasıl yapılır: Windows Forms denetimi için komut yönlendirme ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `Initialize` Bunu yapmak için.

##  <a name="icommandui_interface"></a>  Icommanduı arabirimi

Kullanıcı arabirimi komutları yönetir.

```
interface class ICommandUI
```

### <a name="remarks"></a>Açıklamalar

Bu arabirim, yöntemleri ve kullanıcı arabirimi komutlarını Yönet özellikleri sağlar. `ICommandUI` benzer [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md)dışında `ICommandUI` .NET bileşenleri ile birlikte çalışmak MFC uygulamaları için kullanılır.

`ICommandUI` içinde kullanılan bir `ON_UPDATE_COMMAND_UI` işleyici türetilmiş sınıf içinde. Bir uygulamanın kullanıcı (seçer veya tıklama) etkinleştirirken her bir menü öğesi bir menü etkin olarak görüntülenen veya devre dışı. Her menü komut hedefinin uygulayarak bu bilgileri sağlar. bir `ON_UPDATE_COMMAND_UI` işleyici. Her komut kullanıcı arabirimi nesnelerinin uygulamanızdaki bir ileti eşleme girişi ve işlev prototipi her işleyicisi oluşturmak için Özellikler penceresini kullanın.

İlgili daha fazla bilgi için `ICommandUI` arabirimi komut yönlendirme olarak kullanılır, bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme Ekle](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Kullanıcı arabirimi komutları MFC'de nasıl yönetildiği hakkında daha fazla bilgi için bkz. [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md).

##  <a name="check"></a>  ICommandUI::Check

Bu komut için kullanıcı arabirimi öğesi için uygun onay durumunu ayarlar.

```
property UICheckState Check;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Ayarlama `Check` aşağıdaki değerleri için:

|Terim|Tanım|
|----------|----------------|
|0|Seçeneğinin işaretini kaldırın|
|1.|Onay|
|2|Belirsiz ayarlayın|

##  <a name="continuerouting"></a>  ICommandUI::ContinueRouting

Aşağı zinciri işleyicileri geçerli ileti yönlendirme devam etmek için komut yönlendirme mekanizması söyler.

```
void ContinueRouting();
```

### <a name="remarks"></a>Açıklamalar

Bu ile birlikte kullanılması gereken bir Gelişmiş bir üye işlevidir bir [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) işleyici false değerini döndürür. Daha fazla bilgi için bkz. Teknik Not [TN006: ileti eşlemeleri](../../mfc/tn006-message-maps.md).

##  <a name="enabled"></a>  ICommandUI::Enabled

Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.

```
property bool Enabled;
```

### <a name="remarks"></a>Açıklamalar

Bu özelliği etkinleştirir veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır. Ayarlama `Enabled` öğeyi devre dışı bırakmak için FALSE etkinleştirmek için true.

##  <a name="id"></a>  ICommandUI::ID

Tarafından temsil edilen kullanıcı arabirimi nesnesi Kimliğini alır `ICommandUI` nesne.

```
property unsigned int ID;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik ' % s'kimliği (tanıtıcısı) menü öğesinin araç çubuğu düğmesini alır veya diğer kullanıcı arabirimi nesnesi temsil ettiği `ICommandUI` nesne.

##  <a name="index"></a>  ICommandUI::Index

Tarafından temsil edilen kullanıcı arabirimi nesnesi indisini alır `ICommandUI` nesne.

```
property unsigned int Index;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik ' % s'dizini (bir tanıtıcı) menü öğesinin araç çubuğu düğmesini alır veya diğer kullanıcı arabirimi nesnesi temsil ettiği `ICommandUI` nesne.

##  <a name="radio"></a>  ICommandUI::Radio

Bu komut için kullanıcı arabirimi öğesi için uygun onay durumunu ayarlar.

```
property bool Radio;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Ayarlama `Radio` öğesi; Aksi takdirde FALSE etkinleştirmek için true.

##  <a name="text"></a>  ICommandUI::Text

Bu komut için kullanıcı arabirimi öğesinin metin ayarlar.

```
property String^ Text;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirimi öğesinin metin ayarlar. Ayarlama `Text` bir metin dizesi işlemek için.

##  <a name="iview_interface"></a>  IView arabirimi

Çeşitli yöntemler uygular, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yönetilen bir denetim için görünüm bildirimlerini göndermek için kullanır.

```
interface class IView
```

### <a name="remarks"></a>Açıklamalar

`IView` çeşitli yöntemler uygular, `CWinFormsView` barındırılan ve yönetilen bir denetime genel görünümü bildirimleri iletecek şekilde kullanır. Bunlar [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) ve [OnActivateView](../../mfc/reference/iview-interface.md).

`IView` benzer [CView](../../mfc/reference/cview-class.md), ancak yalnızca yönetilen görünümleri ve denetimleri ile kullanılır.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="onactivateview"></a>  IView::OnActivateView

Bir görünümü etkinleştirmek veya MFC tarafından çağrılır.

```
void OnActivateView(bool activate);
```

### <a name="parameters"></a>Parametreler

*Etkinleştirme*<br/>
Görünüm belirtir etkin veya devre dışı.

##  <a name="oninitialupdate"></a>  IView::OnInitialUpdate

Görünüm ilk belgeye eklendikten sonra ancak görünüm başlangıçta görüntülenmeden önce framework tarafından çağırılır.

```
void OnInitialUpdate();
```

##  <a name="onupdate"></a>  IView::OnUpdate

MFC tarafından görünümün belge değiştirildikten sonra çağırılır.

```
void OnUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev görünümünü değişiklikleri yansıtacak şekilde güncelleştirilecek görünümü sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek Topla](../../visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

