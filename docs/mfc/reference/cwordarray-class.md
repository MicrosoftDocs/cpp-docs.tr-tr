---
title: CWordArray sınıfı
ms.date: 09/07/2019
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
ms.openlocfilehash: c136bbb14e0d7cffc604813731b6f87ba18063cf
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907907"
---
# <a name="cwordarray-class"></a>CWordArray sınıfı

16-bit sözcüklerdeki dizileri destekler.

## <a name="syntax"></a>Sözdizimi

```
class CWordArray : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin `CWordArray` üye işlevleri [CObArray](../../mfc/reference/cobarray-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, üye işlevi özellikleri için `CObArray` başvuru belgelerini kullanabilirsiniz. Bir [CObject](../../mfc/reference/cobject-class.md) işaretçisini işlev parametresi veya dönüş değeri olarak gördüğünüz her yerde, bir kelime yerine koyun.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, öğesine çevirir

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObArray:: CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray:: Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğesi ekler; gerekirse diziyi büyür.|
|[CObArray:: Append](../../mfc/reference/cobarray-class.md#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyür.|
|[CObArray:: Copy](../../mfc/reference/cobarray-class.md#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CObArray:: ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru döndürür.|
|[CObArray:: FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınırın üzerinde kullanılmayan tüm belleği serbest bırakır.|
|[CObArray:: GetAt](../../mfc/reference/cobarray-class.md#getat)|Verilen dizindeki değeri döndürür.|
|[CObArray:: GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CObArray:: GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişime izin verir. NULL olabilir.|
|[CObArray:: GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CObArray:: Getüstsınırı](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizini döndürür.|
|[CObArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CObArray:: IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizinin boş olup olmadığını belirler.|
|[CObArray:: RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CObArray:: RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CObArray:: SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CObArray:: SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|
|[CObArray:: SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide yer alan öğelerin sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray:: işleci&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CWordArray`öğelerinin serileştirilmesi ve dökümünü desteklemek için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu ekler. Bir sözcük dizisi, aşırı yüklenmiş bir ekleme işleci veya [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) üye işlevi ile bir arşive depolanıyorsa, her öğe sırasıyla serileştirilmiş olur.

> [!NOTE]
>  Bir dizi kullanmadan önce, boyutunu `SetSize` belirlemek ve için bellek ayırmak üzere kullanın. Kullanmıyorsanız `SetSize`, diziye öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

Dizideki ayrı öğelerin bir dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Kullanma `CWordArray`hakkında daha fazla bilgi için bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

##  <a name="icommandsource_interface"></a>ICommandSource arabirimi

Bir komut kaynak nesnesinden kullanıcı denetimine gönderilen komutları yönetir.

```
interface class ICommandSource
```

### <a name="remarks"></a>Açıklamalar

Bir MFC görünümünde bir Kullanıcı Denetimi barındırdığınızda, [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md) komutları YÖNLENDIRIR ve MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesini sağlamak IÇIN komut UI iletilerini Kullanıcı denetimine güncelleştirir. Uygulayarak, Kullanıcı denetimine `ICommandSource` nesnesine bir başvuru verirsiniz.

Bkz [. nasıl yapılır: Öğesinin nasıl kullanılacağına `ICommandTarget`ilişkin bir örnek için](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) Windows Forms denetimine komut yönlendirmesi ekleyin.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="addcommandhandler"></a>ICommandSource:: AddCommandHandler

Komut kaynak nesnesine bir komut işleyicisi ekler.

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.

*cmdHandler*<br/>
Komut işleyici yöntemine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem komut işleyicisi *cmdHandler* komutunu komut kaynak nesnesine ekler ve Işleyiciyi *cmdID*'e eşler.

Bkz [. nasıl yapılır: Öğesinin nasıl kullanılacağına `AddCommandHandler`ilişkin bir örnek için](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) Windows Forms denetimine komut yönlendirmesi ekleyin.

##  <a name="addcommandrangehandler"></a>ICommandSource:: AddCommandRangeHandler

Komut kaynak nesnesine bir komut işleyicileri grubu ekler.

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.

*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.

*cmdHandler*<br/>
Komutların eşlendiği ileti işleyicisi yöntemine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bitişik bir komut kimliği aralığını tek bir ileti işleyicisine eşleştirir ve komut kaynak nesnesine ekler. Bu, bir ilişkili düğme grubunu tek bir yöntemle işlemek için kullanılır.

##  <a name="addcommandrangeuihandler"></a>ICommandSource:: Addcommandrangeuıhandler

Komut kaynak nesnesine bir kullanıcı arabirimi komut ileti işleyicileri grubu ekler.

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.

*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.

*cmdHandler*<br/>
Komutların eşlendiği ileti işleyicisi yöntemine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bitişik bir komut kimliği aralığını tek bir kullanıcı arabirimi komut iletisi işleyicisine eşleştirir ve komut kaynak nesnesine ekler. Bu, bir ilişkili düğme grubunu tek bir yöntemle işlemek için kullanılır.

##  <a name="addcommanduihandler"></a>ICommandSource:: AddCommandUIHandler

Komut kaynak nesnesine bir kullanıcı arabirimi komut iletisi işleyicisi ekler.

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.

*cmdUIHandler*<br/>
Kullanıcı arabirimi komut iletisi işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesine kullanıcı arabirimi komut iletisi işleyicisi *cmdHandler* ' i ekler ve Işleyiciyi *cmdID*'e eşler.

##  <a name="postcommand"></a>ICommandText::P Ostsource:

İşlenmek üzere beklemeden bir ileti gönderir.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*komutundaki*<br/>
Nakledilecek iletinin komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *komut*tarafından belirtilen kimliğe eşlenen iletiyi zaman uyumsuz olarak gönderir. İletiyi pencerenin ileti kuyruğuna yerleştirmek için [CWnd::P ostMessage](../../mfc/reference/cwnd-class.md#postmessage) çağırır ve sonra karşılık gelen pencerenin iletiyi işlemesini beklemeden geri döndürür.

##  <a name="removecommandhandler"></a>ICommandSource:: RemoveCommandHandler

Komut işleyicisini bir komut kaynak nesnesinden kaldırır.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *cmdID* ile eşlenen komut işleyicisini komut kaynak nesnesinden kaldırır.

##  <a name="removecommandrangehandler"></a>ICommandSource:: RemoveCommandRangeHandler

Bir komut işleyici grubunu bir komut kaynak nesnesinden kaldırır.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.

*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesinden *cmdIDMin* ve *Cmdidmax*tarafından belirtilen komut kimlikleriyle eşlenmiş bir ileti işleyicileri grubunu kaldırır.

##  <a name="removecommandrangeuihandler"></a>ICommandSource:: Removecommandrangeuıhandler

Bir komut kaynak nesnesinden bir kullanıcı arabirimi komut ileti işleyicileri grubunu kaldırır.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.

*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesinden *cmdIDMin* ve *Cmdidmax*tarafından belirtilen komut kimlikleriyle eşlenmiş bir kullanıcı arabirimi komut ileti işleyicileri grubunu kaldırır.

##  <a name="removecommanduihandler"></a>ICommandSource:: RemoveCommandUIHandler

Bir komut kaynak nesnesinden bir kullanıcı arabirimi komut iletisi işleyicisini kaldırır.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesinden *cmdID* ile eşlenen kullanıcı arabirimi komut iletisi işleyicisini kaldırır.

##  <a name="sendcommand"></a>ICommandSource:: SendCommand

Bir ileti gönderir ve döndürmeden önce işlenmesini bekler.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*komutundaki*<br/>
Gönderilecek iletinin komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *komut*tarafından belirtilen kimliğe eşlenen iletiyi eşzamanlı olarak gönderir. İletiyi pencerenin ileti kuyruğuna yerleştirmek için [CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) çağırır ve bu pencere yordamı döndürmeden önce iletiyi işleyene kadar bekler.

##  <a name="icommandtarget_interface"></a>ICommandTarget arabirimi

Komut kaynak nesnesinden komutları almak için arabirimi olan bir kullanıcı denetimi sağlar.

```
interface class ICommandTarget
```

### <a name="remarks"></a>Açıklamalar

Bir MFC görünümünde Kullanıcı denetimini barındırdığınızda, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) ve MFC komutlarının (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesini sağlamak IÇIN komut UI iletilerini Kullanıcı denetimine yönlendirir. Uygulayarak `ICommandTarget`, Kullanıcı denetimine nesnesine bir başvuru verirsiniz.

Bkz [. nasıl yapılır: Öğesinin nasıl kullanılacağına `ICommandTarget`ilişkin bir örnek için](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) Windows Forms denetimine komut yönlendirmesi ekleyin.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="initialize"></a>ICommandTarget:: Initialize

Komut hedef nesnesini başlatır.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parametreler

*cmdSource*<br/>
Komut kaynak nesnesine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bir MFC görünümünde bir Kullanıcı Denetimi barındırdığınızda, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) komutunu YÖNLENDIRIR ve MFC komutlarının işlemesini sağlamak IÇIN komut UI iletilerini Kullanıcı denetimine güncelleştirir.

Bu yöntem, komut hedef nesnesini başlatır ve belirtilen komut kaynağı nesnesi *cmdSource*ile ilişkilendirir. Kullanıcı denetim sınıfı uygulamasında çağrılmalıdır. Başlatma sırasında, `Initialize` uygulamadaki [ıomtionsource:: AddCommandHandler](../../mfc/reference/icommandsource-interface.md) öğesini çağırarak komut işleyicilerini komut kaynak nesnesiyle kaydetmeniz gerekir. Bkz [. nasıl yapılır: Bunu yapmak için kullanılacak](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `Initialize` bir örnek için Windows Forms denetimine komut yönlendirmesi ekleyin.

##  <a name="icommandui_interface"></a>Iommanduı arabirimi

Kullanıcı arabirimi komutlarını yönetir.

```
interface class ICommandUI
```

### <a name="remarks"></a>Açıklamalar

Bu arabirim, Kullanıcı arabirimi komutlarını yöneten Yöntemler ve özellikler sağlar. `ICommandUI`, [CCmdUI sınıfına](../../mfc/reference/ccmdui-class.md)benzerdir, ancak `ICommandUI` .NET bileşenleriyle birlikte çalışan MFC uygulamaları için kullanılır.

`ICommandUI`, türetilmiş bir sınıftaki `ON_UPDATE_COMMAND_UI` bir işleyici içinde kullanılır. Bir uygulamanın kullanıcısı bir menüyü etkinleştirir (seçer veya tıklatır), her menü öğesi etkin veya devre dışı olarak görüntülenir. Her menü komutunun hedefi, bir `ON_UPDATE_COMMAND_UI` işleyici uygulayarak bu bilgileri sağlar. Uygulamanızdaki her bir komut Kullanıcı arabirimi nesnesi için, her işleyici için bir ileti eşleme girişi ve işlev prototipi oluşturmak üzere [sınıf Sihirbazı](mfc-class-wizard.md) 'Nı veya **özellikler** penceresini ( **sınıf görünümü**) kullanın.

`ICommandUI` Arabirimin komut yönlendirmesinde nasıl kullanıldığı hakkında daha fazla bilgi için bkz [. nasıl yapılır: Windows Forms denetimine](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)komut yönlendirmesi ekleyin.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Kullanıcı arabirimi komutlarının MFC 'de nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CCmdUI sınıfı](../../mfc/reference/ccmdui-class.md).

##  <a name="check"></a>ICommandUI:: Check

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.

```
property UICheckState Check;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar. Aşağıdaki `Check` değerlere ayarlayın:

|Terim|Tanım|
|----------|----------------|
|0|Kutunun|
|1\.|Onay|
|2|Belirsiz ayarla|

##  <a name="continuerouting"></a>Iommanduı:: Devamsallama

Komut yönlendirme mekanizmasına, geçerli iletiyi işleyiciler zincirinin altına yönlendirmeye devam etmeyi söyler.

```
void ContinueRouting();
```

### <a name="remarks"></a>Açıklamalar

Bu, FALSE döndüren bir [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) işleyicisiyle birlikte kullanılması gereken gelişmiş bir üye işlevdir. Daha fazla bilgi için bkz. Teknik [notTN006: İleti haritaları](../../mfc/tn006-message-maps.md).

##  <a name="enabled"></a>Iommanduı:: etkin

Bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır.

```
property bool Enabled;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır. Öğeyi `Enabled` etkinleştirmek için true, devre dışı bırakmak için false olarak ayarlayın.

##  <a name="id"></a>Iommanduı:: ID

`ICommandUI` Nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin kimliğini alır.

```
property unsigned int ID;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, `ICommandUI` nesne tarafından temsil edilen menü öğesi, araç çubuğu düğmesi veya diğer kullanıcı arabirimi nesnesinin kimliğini (bir tanıtıcı) alır.

##  <a name="index"></a>Iommanduı:: Index

`ICommandUI` Nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin dizinini alır.

```
property unsigned int Index;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, `ICommandUI` nesne tarafından temsil edilen menü öğesi, araç çubuğu düğmesi veya diğer kullanıcı arabirimi nesnesinin dizinini (bir tanıtıcı) alır.

##  <a name="radio"></a>Iommanduı:: Radio

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.

```
property bool Radio;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar. Öğeyi `Radio` etkinleştirmek için true olarak ayarlayın; Aksi takdirde false.

##  <a name="text"></a>ICommandUI:: metin

Bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar.

```
property String^ Text;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar. Bir `Text` metin dizesi tanıtıcısına ayarlayın.

##  <a name="iview_interface"></a>IView arabirimi

, Yönetilen bir denetime görüntüleme bildirimleri göndermek için [CWinFormsView](../../mfc/reference/cwinformsview-class.md) tarafından kullanılan çeşitli yöntemler uygular.

```
interface class IView
```

### <a name="remarks"></a>Açıklamalar

`IView`ortak görünüm bildirimlerini barındırılan `CWinFormsView` yönetilen bir denetime iletmek için kullanan çeşitli yöntemler uygular. Bunlar [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) ve [OnActivateView](../../mfc/reference/iview-interface.md)' dir.

`IView`, [CView](../../mfc/reference/cview-class.md)öğesine benzerdir, ancak yalnızca yönetilen görünümler ve denetimler ile kullanılır.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="onactivateview"></a>IView:: OnActivateView

Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında MFC tarafından çağırılır.

```
void OnActivateView(bool activate);
```

### <a name="parameters"></a>Parametreler

*etkinleştir*<br/>
Görünümün etkinleştirildiğini veya devre dışı bırakıldığını gösterir.

##  <a name="oninitialupdate"></a>IView:: OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra, ancak görünüm ilk görüntülenmeden önce Framework tarafından çağırılır.

```
void OnInitialUpdate();
```

##  <a name="onupdate"></a>IView:: OnUpdate

Görünümün belgesi değiştirildikten sonra MFC tarafından çağırılır.

```
void OnUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, görünümün değişiklikleri yansıtacak şekilde görünümünü güncelleştirmesine izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
