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
ms.openlocfilehash: bf19865b4c11bb8305bea62b3682faebe39bef74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cwordarray-class"></a>CWordArray sınıfı
16 bit sözcükler dizileri destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CWordArray` sınıfının üye fonksiyonları benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullandığınız `CObArray` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir [CObject](../../mfc/reference/cobject-class.md) işaretçi bir işlev parametresi veya dönüş değeri olarak yerine bir **WORD**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Örneğin, çevrilir  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Bir öğeyi dizinin sonuna ekler; dizi gerekirse artar.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Başka bir dizi diziye ekler; dizi gerekirse artar.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Başka bir dizi diziye kopyalar; dizi gerekirse artar.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi öğesi işaretçinin geçici bir başvuru döndürür.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli bir üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirtilen dizindeki değeri döndürür.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizide öğe sayısını alır.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. Olabilir **NULL**.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizide öğe sayısını alır.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizinini döndürür.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Bir öğenin (veya başka bir dizinin tüm öğeleri) belirtilen bir dizinde ekler.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizi boş olup olmadığını belirler.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizisinden tüm öğeleri kaldırır.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizinindeki bir öğeyi kaldırır.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizine için değeri ayarlar; dizi büyümeye izin verilmiyor.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizine için değeri ayarlar; dizi gerekirse artar.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide dahil edilmek üzere öğe sayısını ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CWordArray` bir araya getirir [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu seri hale getirme ve alt öğeleri dökme desteklemek için. Aşırı yüklenmiş ekleme işleciyle veya ile bir arşiv sözcükler dizisi depolanıyorsa [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) üye işlevi her öğesidir, sırayla, seri hale getirilmiş.  
  
> [!NOTE]
>  Bir dizi kullanmadan önce kullanın `SetSize` boyutuna kurmak ve bunun için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, dizinizi için öğe eklemek görüntülenmesine neden olur sık bırakılan ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara.  
  
 Dizideki ayrı ayrı öğeler dökümünü gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
 Kullanma hakkında daha fazla bilgi için `CWordArray`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>  ICommandSource arabirimi  
 Bir kullanıcı denetimi için bir komut kaynak nesneden gönderilen komutları yönetir.  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>Açıklamalar  
 MFC görünümü, bir kullanıcı denetimi barındırdığınızda [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md) yollar komutlar ve güncelleştirme komut MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemeye izin vermek için kullanıcı denetimi UI iletileri. Uygulayarak, kullanıcı denetimi için bir başvuru size `ICommandSource` nesnesi.  
  
 Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler  
 Bir komut işleyici için bir komut kaynak nesnesi ekler.  
  
```  
void AddCommandHandler(
    unsigned int cmdID,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdID`  
 Komut kimliği.  
  
 `cmdHandler`  
 Komut işleyici yöntemi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem komut işleyici ekler `cmdHandler` komut kaynak nesnesi için ve işleyiciye eşler `cmdID`.  
  
 Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `AddCommandHandler`.  
  
##  <a name="addcommandrangehandler"></a>  ICommandSource::AddCommandRangeHandler  
 Komut işleyicileri bir grup için bir komut kaynak nesnesi ekler.  
  
```  
void AddCommandRangeHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdIDMin`  
 Komut Kimliği aralığın başlangıç dizini.  
  
 `cmdIDMax`  
 Komut Kimliği aralığı bitiş dizini.  
  
 `cmdHandler`  
 Komutları eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için tek bir ileti işleyicisi komut kimlikleri bitişik bir dizi eşler ve komut kaynak nesnesi ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.  
  
##  <a name="addcommandrangeuihandler"></a>  ICommandSource::AddCommandRangeUIHandler  
 Kullanıcı arabirimi komutu ileti işleyicileri bir grup için bir komut kaynak nesnesi ekler.  
  
```  
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,   
    unsigned int cmdIDMax,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdIDMin`  
 Komut Kimliği aralığın başlangıç dizini.  
  
 `cmdIDMax`  
 Komut Kimliği aralığı bitiş dizini.  
  
 `cmdHandler`  
 Komutları eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için tek bir kullanıcı arabirimi komutu ileti işleyicisi komut kimlikleri bitişik bir dizi eşler ve komut kaynak nesnesi ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.  
  
##  <a name="addcommanduihandler"></a>  ICommandSource::AddCommandUIHandler  
 Bir kullanıcı arabirimi komutu ileti işleyicisi için bir komut kaynak nesnesi ekler.  
  
```  
void AddCommandUIHandler(
    unsigned int cmdID,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdID`  
 Komut kimliği.  
  
 `cmdUIHandler`  
 Kullanıcı arabirimi komutu ileti işleyicisi yöntemi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem kullanıcı arabirimi komutu ileti işleyicisini ekler `cmdHandler` komut kaynak nesnesi için ve işleyiciye eşler `cmdID`.  
  
##  <a name="postcommand"></a>  ICommandSource::PostCommand  
 Bu işlenmeyi bekleyen olmadan bir ileti gönderir.  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Parametreler  
 `command`  
 İletinin postalama komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından belirtilen kimliği eşlenmiş ileti zaman uyumsuz olarak gönderir `command`. Çağırır [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) iletiyi işlemek karşılık gelen pencerenin beklemeden pencere ileti sırası ve sonra geri ileti yerleştirmek için.  
  
##  <a name="removecommandhandler"></a>  ICommandSource::RemoveCommandHandler  
 Bir komut işleyici komutu kaynak nesnesinden kaldırır.  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdID`  
 Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem eşlenen komut işleyici kaldırır `cmdID` komut kaynak nesnesi.  
  
##  <a name="removecommandrangehandler"></a>  ICommandSource::RemoveCommandRangeHandler  
 Komut işleyicileri bir grup komutu kaynak nesnesinden kaldırır.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdIDMin`  
 Komut Kimliği aralığın başlangıç dizini.  
  
 `cmdIDMax`  
 Komut Kimliği aralığı bitiş dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından komut kimlikleri belirtilen eşlenmiş ileti işleyicileri birtakım kaldırır `cmdIDMin` ve `cmdIDMax`, komut kaynak nesnesi.  
  
##  <a name="removecommandrangeuihandler"></a>  ICommandSource::RemoveCommandRangeUIHandler  
 Bir grup kullanıcı arabirimi komutu ileti işleyicileri komutu kaynak nesnesinden kaldırır.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdIDMin`  
 Komut Kimliği aralığın başlangıç dizini.  
  
 `cmdIDMax`  
 Komut Kimliği aralığı bitiş dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından komut kimlikleri belirtilen eşlenen kullanıcı arabirimi komutu ileti işleyicileri, bir grup kaldırır `cmdIDMin` ve `cmdIDMax`, komut kaynak nesnesi.  
  
##  <a name="removecommanduihandler"></a>  ICommandSource::RemoveCommandUIHandler  
 Bir kullanıcı arabirimi komutu ileti işleyicisi komutu kaynak nesnesinden kaldırır.  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdID`  
 Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem eşlenen kullanıcı arabirimi komutu ileti işleyicisi kaldırır `cmdID` komut kaynak nesnesi.  
  
##  <a name="sendcommand"></a>  ICommandSource::SendCommand  
 Bir ileti gönderir ve döndürmeden önce işlenecek bekler.  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Parametreler  
 `command`  
 Gönderilecek ileti komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, zaman uyumlu olarak tarafından belirtilen kimliği eşlenmiş ileti gönderir `command`. Çağırır [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) Bu pencere yordamı döndürmeden önce iletiyi işleyene kadar pencere ileti sırası ve bekler ileti yerleştirmek için.  
  
##  <a name="icommandtarget_interface"></a>  ICommandTarget arabirimi  
 Bir kullanıcı denetimi komutlar bir komut kaynak nesneden almak için bir arabirim sağlar.  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>Açıklamalar  
 MFC görünümü, bir kullanıcı denetimi barındırdığınızda [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yollar komutlar ve güncelleştirme komut MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemeye izin vermek için kullanıcı denetimi UI iletileri. Uygulama tarafından `ICommandTarget`, kullanıcı denetimi nesneye bir başvurusu verin.  
  
 Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="initialize"></a>  ICommandTarget::Initialize'ı  
 Komut hedefi nesnesini başlatır.  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdSource`  
 Komut kaynak nesnesi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 MFC görünümü, bir kullanıcı denetimi barındırdığınızda [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yollar komutlar ve güncelleştirme komut MFC komutlarını işlemeye izin vermek için kullanıcı denetimi UI iletileri.  
  
 Bu yöntem komutu hedef nesnesini başlatır ve belirtilen komut kaynak nesnesi ile ilişkilendirir `cmdSource`. Kullanıcı denetimi sınıfı uygulamasında çağrılmalıdır. Başlatma sırasında komut işleyicileri komut kaynak nesnesi ile çağırarak kaydedeceğini [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) içinde `Initialize` uygulaması. Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `Initialize` Bunu yapmak için.  
  
##  <a name="icommandui_interface"></a>  ICommandUI arabirimi  
 Kullanıcı arabirimi komutları yönetir.  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu arabirim yöntemleri ve kullanıcı arabirimi komutları yönetmek özellikleri sağlar. `ICommandUI` benzer [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md)dışında `ICommandUI` .NET bileşenleriyle birlikte MFC uygulamalarında kullanılır.  
  
 `ICommandUI` içinde kullanılan bir `ON_UPDATE_COMMAND_UI` işleyicisi türetilmiş sınıf içinde. Bir kullanıcı bir uygulamanın (seçer veya tıklama) etkinleştirdiğinde menüsünde, her bir menü öğesi etkin olarak görüntülenir veya devre dışı. Her menü komut hedefinin uygulayarak bu bilgileri sağlar. bir `ON_UPDATE_COMMAND_UI` işleyicisi. Her komut kullanıcı arabirimi nesneleri uygulamanızda için her işleyicisi için işlev prototipi ve ileti eşleme girişi oluşturmak için Özellikler penceresini kullanın.  
  
 Nasıl hakkında daha fazla bilgi için `ICommandUI` arabirimi komut yönlendirme kullanılır, bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Kullanıcı arabirimi komutları MFC'de nasıl yönetildiğini daha fazla bilgi için bkz: [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="check"></a>  ICommandUI::Check  
 Bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar.  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu özellik bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Ayarlama `Check` aşağıdaki değerleri için:  
  
|Terim|Tanım|  
|----------|----------------|  
|0|Seçeneğinin işaretini kaldırın|  
|1.|Onay|  
|2|Belirsiz ayarlayın|  
  
##  <a name="continuerouting"></a>  ICommandUI::ContinueRouting  
 Geçerli ileti işleyicileri zincirine aşağı yönlendirme devam etmek için komut yönlendirme mekanizması söyler.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte kullanılması gereken bir Gelişmiş üye işlevi budur bir [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) döndürür işleyici `FALSE`. Daha fazla bilgi için bkz. Teknik Not [TN006: ileti eşlemeleri](../../mfc/tn006-message-maps.md).  
  
##  <a name="enabled"></a>  ICommandUI::Enabled  
 Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu özellik sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır. Ayarlama `Enabled` için `TRUE` öğeyi etkinleştirmek için `FALSE` devre dışı bırakmak için.  
  
##  <a name="id"></a>  ICommandUI::ID  
 Tarafından temsil edilen kullanıcı arabirimi nesnesinin kimliği alır `ICommandUI` nesnesi.  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu özellik menü öğesi, araç çubuğu düğmesi (tanıtıcı) Kimliğini alır veya diğer kullanıcı arabirimi nesnesinin temsil ettiği `ICommandUI` nesnesi.  
  
##  <a name="index"></a>  ICommandUI::Index  
 Tarafından temsil edilen kullanıcı arabirimi nesnesi dizinini alır `ICommandUI` nesnesi.  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu özellik menü öğesi, araç çubuğu düğmesi (tanıtıcı) dizinini alır veya diğer kullanıcı arabirimi nesnesinin temsil ettiği `ICommandUI` nesnesi.  
  
##  <a name="radio"></a>  ICommandUI::Radio  
 Bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar.  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu özellik bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Ayarlama `Radio` için `TRUE` ; öğeyi etkinleştirmek için aksi `FALSE`.  
  
##  <a name="text"></a>  ICommandUI::Text  
 Bu komut için kullanıcı arabirimi öğesi metni ayarlar.  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu özellik, bu komut için kullanıcı arabirimi öğesi metni ayarlar. Ayarlama `Text` bir metin dizesi işlenecek.  
  
##  <a name="iview_interface"></a>  IView arabirimi  
 Birkaç yöntemlerini uygular, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) için yönetilen bir denetimin görünüm bildirimleri göndermek için kullanır.  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `IView` birkaç yöntemlerini uygular, `CWinFormsView` yönetilen bir barındırılan denetime genel görünümü bildirimleri kullanır. Bunlar [OnInitialUpdate](../../mfc/reference/iview-interface.md), [in](../../mfc/reference/iview-interface.md) ve [OnActivateView](../../mfc/reference/iview-interface.md).  
  
 `IView` benzer [CView](../../mfc/reference/cview-class.md), ancak yalnızca yönetilen görünümler ve denetimleri ile kullanılır.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="onactivateview"></a>  IView::OnActivateView  
 Bir görünüm etkinleştirilmiş veya devre dışı olduğunda MFC tarafından çağrılır.  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>Parametreler  
 `activate`  
 Görünüm belirtir etkin veya devre dışı.  
  
##  <a name="oninitialupdate"></a>  IView::OnInitialUpdate  
 Görünüm ilk belgeye eklendikten sonra ancak görünümü başlangıçta görüntülenmeden önce çerçevesi tarafından çağrılır.  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>  IView::OnUpdate  
 MFC tarafından görünümün belge değiştirildikten sonra çağrılır.  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev görünümünü değişiklikleri yansıtacak şekilde güncelleştirmek görünümü sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



