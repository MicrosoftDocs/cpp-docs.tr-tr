---
title: Temsilci ve arabirim eşleme makroları (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: 8f48b916f7130551fc8d4da5bb2ebc75d8d728d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322988"
---
# <a name="delegate-and-interface-map-macros"></a>Temsilci ve arabirim eşleme makroları

MFC, temsilci ve arabirim eşlemeleri için bu makrolar destekler:

|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Bir temsilci harita başlar.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Tanımı interfaced harita başlar.|
|[CommandHandler temsilcisi](#commandhandler)|Geri çağırma yöntemleri ile bir komut kaynak kaydeder.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Bir temsilci harita sona erer.|
|[END_INTERFACE_MAP](#end_interface_map)|Arabirim eşlemesini uygulama dosyasında sona erer. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Temsilci haritada bir giriş oluşturur.|
|[INTERFACE_PART](#interface_part)|Nesnenizin destekleyeceği her arabirim için makro begın_ınterface_map ve end_ınterface_map makrosu arasında kullanılır.|
|[MAKE_DELEGATE](#make_delegate)|Yönetilen bir denetim için bir olay işleyicisi ekler.|

## <a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP

Bir temsilci harita başlar.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>Parametreler

*SINIFI*<br/>
Yönetilen denetim barındıran sınıf.

### <a name="remarks"></a>Açıklamalar

Bu makro bir temsilci harita oluşturma temsilci girişlerinin listesini başlangıcını işaretler. Bu makro nasıl kullanıldığına dair bir örnek için bkz: [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Gereksinimler

**Başlık:** msclr\event.h

##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

V souboru implementace kullanıldığında interfaced eşleme tanımı başlar.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Arabirim eşlemesi tanımlanmış olduğu sınıfı

*baseClass*<br/>
Sınıf *sınıfın* türetir.

### <a name="remarks"></a>Açıklamalar

Uygulanan her arabirim için bir veya daha fazla ınterface_part makrosu çağrılarını yoktur. Sınıfın kullandığı her toplama için bir ınterface_aggregate makro çağrısı vardır.

Arabirim eşlemeleri hakkında daha fazla bilgi için bkz. [Teknik Not 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="commandhandler"></a>CommandHandler temsilcisi

Geri çağırma yöntemleri ile bir komut kaynak kaydeder.

### <a name="syntax"></a>Sözdizimi

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu temsilci, geri çağırma yöntemleri ile bir komut kaynak kaydeder. Komut kaynak nesnesine bir temsilci eklediğinizde, geri çağırma yöntemi, belirtilen kaynaktan gelen komutların için bir işleyici haline gelir.

Daha fazla bilgi için [nasıl yapılır: Ekle komutu yönlendirme için bir Windows Forms denetimi](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll içinde tanımlanmıştır)

##  <a name="commanduihandler"></a>Commanduıhandler

Geri çağırma yöntemleri ile bir kullanıcı arabirimi güncelleştirme komut iletisi kaydeder.

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

Bu temsilci, geri çağırma yöntemleri ile bir kullanıcı arabirimi güncelleştirme komut iletisi kaydeder. `CommandUIHandler` benzer [CommandHandler](#commandhandler) dışında bu temsilci kullanıcı arabirimi nesnesi güncelleştirme komutları ile kullanılır. Kullanıcı arabirimini güncelleştirme komutları bire bir ileti işleyicisi yöntemleri ile eşlenmelidir.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll içinde tanımlanmıştır)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP

Bir temsilci harita sona erer.

### <a name="syntax"></a>Sözdizimi

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>Açıklamalar

Bu makro, bir temsilci harita oluşturma temsilci girişlerinin listesini sonunu işaretler. Bu makro nasıl kullanıldığına dair bir örnek için bkz: [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Gereksinimler

**Başlık:** msclr\event.h

##  <a name="end_interface_map"></a>END_INTERFACE_MAP

Arabirim eşlemesini uygulama dosyasında sona erer.

### <a name="syntax"></a>Sözdizimi

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>Açıklamalar

Arabirim eşlemeleri hakkında daha fazla bilgi için bkz: [Teknik Not 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

Temsilci haritada bir giriş oluşturur.

### <a name="syntax"></a>Sözdizimi

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>Parametreler

*ÜYESİ*<br/>
Denetimine eklenecek olay işleyicisi yöntemi.

*ARG0*<br/>
Yönetilen bir olay işleyicisi yönteminde, ilk bağımsız değişkeni gibi `Object^`.

*ARG1*<br/>
Yönetilen bir olay işleyicisi yönteminde, ikinci bağımsız değişkeni gibi `EventArgs^`.

### <a name="remarks"></a>Açıklamalar

Temsilci eşlemedeki her giriş tarafından oluşturulan bir yönetilen bir olay işleyici temsilcisini karşılık gelen [MAKE_DELEGATE](#make_delegate).

### <a name="example"></a>Örnek

Aşağıdaki kod örneği için temsilci eşlemesindeki bir giriş oluşturmak için EVENT_DELEGATE_ENTRY kullanmayı gösterir `OnClick` olay işleyicisi; ayrıca aşağıdaki kod örneğinde MAKE_DELEGATE bakın. Daha fazla bilgi için [nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuz](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** msclr\event.h

##  <a name="interface_part"></a>INTERFACE_PART

Nesnenizin destekleyeceği her arabirim için makro begın_ınterface_map ve end_ınterface_map makrosu arasında kullanılır.

### <a name="syntax"></a>Sözdizimi

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Arabirim eşlemesini içeren sınıfın adı.
*IID*<br/>
Katıştırılmış sınıfla eşleştirilecek olan IID.
*localClass*<br/>
Yerel sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen bir sınıf üyesi için bir IID eşlemenizi sağlar *sınıfın* ve *localClass*.

Arabirim eşlemeleri hakkında daha fazla bilgi için bkz. [Teknik Not 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="make_delegate"></a>MAKE_DELEGATE

Yönetilen bir denetim için bir olay işleyicisi ekler.

### <a name="syntax"></a>Sözdizimi

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>Parametreler

*TEMSİLCİ*<br/>
Yönetilen bir olay işleyicisinin türü temsilcisi, gibi [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True).

*ÜYESİ*<br/>
Denetimine eklenecek olay işleyicisi yönteminin adı.

### <a name="remarks"></a>Açıklamalar

Bu makro türü bir yönetilen bir olay işleyici temsilcisini oluşturur *TEMSİLCİ* ve adının *üye*. Yönetilen bir olay işleyici temsilcisini yönetilen olayları işlemek bir yerel sınıf sağlar.

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde nasıl çağrılacağını gösterir `MAKE_DELEGATE` eklemek için bir `OnClick` MFC denetimi olay işleyicisi `MyControl`. Bu makro bir MFC uygulamasında nasıl çalıştığına ilişkin daha kapsamlı açıklaması için bkz [nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuz](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** msclr\event.h

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Yerel C++ Sınıflarından Havuz Windows Forms Olayları](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[Nasıl yapılır: Windows Forms Denetimine Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
