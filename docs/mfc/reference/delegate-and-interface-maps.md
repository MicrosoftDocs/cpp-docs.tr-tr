---
title: Temsilci ve Arayüz Haritası Makroları (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: e08597d024f5e3a74dcf47363ad3de0aa60cf6c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365829"
---
# <a name="delegate-and-interface-map-macros"></a>Temsilci ve arabirim eşleme makroları

MFC temsilci ve arabirim eşlemleri için bu makroları destekler:

|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Bir temsilci haritası başlasın.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Arabirimli haritanın tanımını başlayır.|
|[CommandHandler Delegesi](#commandhandler)|Geri arama yöntemlerini bir komut kaynağıyla kaydeder.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Temsilci haritasını sona erdirer.|
|[END_INTERFACE_MAP](#end_interface_map)|Uygulama dosyasındaki arabirim eşlemi sona erer. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Temsilci haritasında bir giriş oluşturur.|
|[INTERFACE_PART](#interface_part)|nesnenizin destekleyeceği her arabirim için BEGIN_INTERFACE_MAP makrosu ile END_INTERFACE_MAP makro arasında kullanılır.|
|[MAKE_DELEGATE](#make_delegate)|Bir olay işleyicisini yönetilen denetime bağlar.|

## <a name="begin_delegate_map"></a><a name="begin_delegate_map"></a>BEGIN_DELEGATE_MAP

Bir temsilci haritası başlasın.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>Parametreler

*Sınıfı*<br/>
Yönetilen denetimin barındırıldığı sınıf.

### <a name="remarks"></a>Açıklamalar

Bu makro, temsilci eşlemi oluşturan temsilci girişleri listesinin başlangıcını işaretler. Bu makronun nasıl kullanıldığına bir örnek olarak, [bkz. EVENT_DELEGATE_ENTRY.](#event_delegate_entry)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** msclr\event.h

## <a name="begin_interface_map"></a><a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

Uygulama dosyasında kullanıldığında arabirim haritasının tanımını başlayır.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Arabirim haritasının tanımlanacak sınıf

*Baseclass*<br/>
*TheClass'ın* türetildiği sınıf.

### <a name="remarks"></a>Açıklamalar

Uygulanan her arabirim için bir veya daha fazla INTERFACE_PART makro çağrıları vardır. Sınıfın kullandığı her toplam için bir INTERFACE_AGGREGATE makro çağırma vardır.

Arayüz haritaları hakkında daha fazla bilgi için [Teknik Not 38'e](../tn038-mfc-ole-iunknown-implementation.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="commandhandler-delegate"></a><a name="commandhandler"></a>CommandHandler Delegesi

Geri arama yöntemlerini bir komut kaynağıyla kaydeder.

### <a name="syntax"></a>Sözdizimi

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu temsilci, geri arama yöntemlerini bir komut kaynağıyla kaydeder. Komut kaynağı nesneye bir temsilci eklediğinizde, geri arama yöntemi belirtilen kaynaktan gelen komutlar için bir işleyici olur.

Daha fazla bilgi için [bkz: Windows Forms Denetimine Komut Yönlendirme ekleme.](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (montaj atlmfc\lib\mfcmifc80.dll tanımlanır)

## <a name="commanduihandler"></a><a name="commanduihandler"></a>CommandUIHandler

Geri arama yöntemlerini kullanıcı arabirimi güncelleştirme komut iletisiyle kaydeder.

### <a name="syntax"></a>Sözdizimi

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

*cmdUI*<br/>
Komut ileti kimliği.

### <a name="remarks"></a>Açıklamalar

Bu temsilci, geri arama yöntemlerini kullanıcı arabirimi güncelleştirme komut iletisiyle kaydeder. `CommandUIHandler`bu temsilcinin kullanıcı arabirimi nesne güncelleştirme komutları ile kullanılması dışında [CommandHandler'a](#commandhandler) benzer. Kullanıcı arabirimi güncelleştirme komutları ileti işleyicisi yöntemleriyle bire bir eşlenmelidir.

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (montaj atlmfc\lib\mfcmifc80.dll tanımlanır)

## <a name="end_delegate_map"></a><a name="end_delegate_map"></a>END_DELEGATE_MAP

Temsilci haritasını sona erdirer.

### <a name="syntax"></a>Sözdizimi

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>Açıklamalar

Bu makro, temsilci eşlemi oluşturan temsilci girişleri listesinin sonunu işaretler. Bu makronun nasıl kullanıldığına bir örnek olarak, [bkz. EVENT_DELEGATE_ENTRY.](#event_delegate_entry)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** msclr\event.h

## <a name="end_interface_map"></a><a name="end_interface_map"></a>END_INTERFACE_MAP

Uygulama dosyasındaki arabirim eşlemi sona erer.

### <a name="syntax"></a>Sözdizimi

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>Açıklamalar

Arayüz haritaları hakkında daha fazla bilgi için [Teknik Not 38'e](../tn038-mfc-ole-iunknown-implementation.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="event_delegate_entry"></a><a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

Temsilci haritasında bir giriş oluşturur.

### <a name="syntax"></a>Sözdizimi

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>Parametreler

*Üye*<br/>
Denetime eklenecek olay işleyicisi yöntemi.

*ARG0*<br/>
Yönetilen olay işleyicisi yönteminin ilk `Object^`bağımsız değişkeni, gibi .

*ARG1*<br/>
Yönetilen olay işleyicisi yönteminin ikinci `EventArgs^`bağımsız değişkeni, gibi .

### <a name="remarks"></a>Açıklamalar

Temsilci haritasındaki her [giriş, MAKE_DELEGATE](#make_delegate)tarafından oluşturulan yönetilen olay işleyicisi temsilcisine karşılık gelir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, olay işleyicisi için temsilci haritasında bir giriş oluşturmak için EVENT_DELEGATE_ENTRY nasıl kullanılacağını `OnClick` gösterir; ayrıca MAKE_DELEGATE kod örneğine bakın. Daha fazla bilgi için [bkz: Windows Formlarını Yerel C++ Sınıflarından Batırın.](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** msclr\event.h

## <a name="interface_part"></a><a name="interface_part"></a>INTERFACE_PART

nesnenizin destekleyeceği her arabirim için BEGIN_INTERFACE_MAP makrosu ile END_INTERFACE_MAP makro arasında kullanılır.

### <a name="syntax"></a>Sözdizimi

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Arabirim eşlemini içeren sınıfın adı.
*ııd*<br/>
Gömülü sınıfa eşlenecek olan IID.
*localClass*<br/>
Yerel sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Bu, *TheClass* ve *localClass*tarafından belirtilen sınıfın bir üyesiyle bir IID eşlemenizi sağlar.

Arayüz haritaları hakkında daha fazla bilgi için [Teknik Not 38'e](../tn038-mfc-ole-iunknown-implementation.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="make_delegate"></a><a name="make_delegate"></a>MAKE_DELEGATE

Bir olay işleyicisini yönetilen denetime bağlar.

### <a name="syntax"></a>Sözdizimi

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>Parametreler

*Temsilci*<br/>
[EventHandler](/dotnet/api/system.eventhandler)gibi yönetilen olay işleyicisi temsilcisinin türü.

*Üye*<br/>
Denetime eklenecek olay işleyicisi yönteminin adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, *TÜR DELEGATE* ve ad *ÜYE*yönetilen bir olay işleyicisi temsilcisi oluşturur. Yönetilen olay işleyicisi temsilcisi, yerel sınıfın yönetilen olayları işlemesine olanak tanır.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir `MAKE_DELEGATE` MFC `OnClick` denetimine `MyControl`olay işleyicisi eklemek için nasıl çağrı yapılacağını gösterir. Bu makronun bir MFC uygulamasında nasıl çalıştığına ilişkin daha geniş bir açıklama için [bkz.](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** msclr\event.h

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
