---
description: 'Daha fazla bilgi edinin: temsilci ve arabirim eşleme makroları'
title: Temsilci ve arabirim eşleme makroları (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: 222625514fa0d6d1d683a6ee4098812298f7ed72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220155"
---
# <a name="delegate-and-interface-map-macros"></a>Temsilci ve arabirim eşleme makroları

MFC, temsilci ve arabirim eşlemeleri için bu makroları destekler:

|Ad|Açıklama|
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Bir temsilci eşlemesi başlatır.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Arabirim eşlemesinin tanımını başlatır.|
|[CommandHandler temsilcisi](#commandhandler)|Geri çağırma yöntemlerini bir komut kaynağıyla kaydeder.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Bir temsilci eşlemesini sonlandırır.|
|[END_INTERFACE_MAP](#end_interface_map)|Uygulama dosyasındaki arabirim eşlemesini sonlandırır. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Temsilci eşlemesinde bir giriş oluşturur.|
|[INTERFACE_PART](#interface_part)|Nesnenizin destekleyeceği her arabirim için BEGIN_INTERFACE_MAP makrosu ve END_INTERFACE_MAP makrosu arasında kullanılır.|
|[MAKE_DELEGATE](#make_delegate)|Yönetilen denetime bir olay işleyicisi ekler.|

## <a name="begin_delegate_map"></a><a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP

Bir temsilci eşlemesi başlatır.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>Parametreler

*SıNıFı*<br/>
Yönetilen denetimin barındırıldığı sınıf.

### <a name="remarks"></a>Açıklamalar

Bu makro, temsilci Haritası oluşturan bir temsilci girdileri listesinin başlangıcını işaretler. Bu makronun nasıl kullanıldığına ilişkin bir örnek için bkz. [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** msclr\event.h

## <a name="begin_interface_map"></a><a name="begin_interface_map"></a> BEGIN_INTERFACE_MAP

Uygulama dosyasında kullanıldığında, arabirim eşlemesinin tanımını başlatır.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Arabirim eşlemesinin tanımlanması gereken sınıf

*baseClass*<br/>
Sınıfı 'ın türetildiği  sınıf.

### <a name="remarks"></a>Açıklamalar

Uygulanan her arabirim için bir veya daha fazla makro çağırma INTERFACE_PART vardır. Sınıfın kullandığı her bir toplama için bir INTERFACE_AGGREGATE makro çağrısı vardır.

Arabirim haritaları hakkında daha fazla bilgi için bkz. [teknik notta 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="commandhandler-delegate"></a><a name="commandhandler"></a> CommandHandler temsilcisi

Geri çağırma yöntemlerini bir komut kaynağıyla kaydeder.

### <a name="syntax"></a>Sözdizimi

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu temsilci, geri çağırma yöntemlerini bir komut kaynağıyla kaydeder. Komut kaynak nesnesine bir temsilci eklediğinizde, geri çağırma yöntemi belirtilen kaynaktan gelen komutlar için bir işleyici haline gelir.

Daha fazla bilgi için bkz. [nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h (derlemede tanımlanan atlmfc\lib\mfcmifc80.dll)

## <a name="commanduihandler"></a><a name="commanduihandler"></a> Öğesindeki CommandUIHandler 'ı

Bir kullanıcı arabirimi güncelleştirme komut iletisiyle geri çağırma yöntemlerini kaydeder.

### <a name="syntax"></a>Sözdizimi

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.

*CmdUI*<br/>
Komut ileti KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu temsilci, geri çağırma yöntemlerini bir kullanıcı arabirimi güncelleştirme komut iletisiyle kaydeder. `CommandUIHandler` , bu temsilcinin Kullanıcı arabirimi nesne güncelleştirme komutlarıyla kullanılması dışında [CommandHandler](#commandhandler) ile benzerdir. Kullanıcı arabirimi güncelleştirme komutları, ileti işleyici yöntemleriyle bire bir ile eşlenmelidir.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h (derlemede tanımlanan atlmfc\lib\mfcmifc80.dll)

## <a name="end_delegate_map"></a><a name="end_delegate_map"></a> END_DELEGATE_MAP

Bir temsilci eşlemesini sonlandırır.

### <a name="syntax"></a>Syntax

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>Açıklamalar

Bu makro, temsilci Haritası oluşturan bir temsilci girdileri listesinin sonunu işaretler. Bu makronun nasıl kullanıldığına ilişkin bir örnek için bkz. [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** msclr\event.h

## <a name="end_interface_map"></a><a name="end_interface_map"></a> END_INTERFACE_MAP

Uygulama dosyasındaki arabirim eşlemesini sonlandırır.

### <a name="syntax"></a>Syntax

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>Açıklamalar

Arabirim haritaları hakkında daha fazla bilgi için bkz. [teknik notta 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="event_delegate_entry"></a><a name="event_delegate_entry"></a> EVENT_DELEGATE_ENTRY

Temsilci eşlemesinde bir giriş oluşturur.

### <a name="syntax"></a>Sözdizimi

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>Parametreler

*ÜYESIDIR*<br/>
Denetime eklenecek olay işleyicisi yöntemi.

*ARG0*<br/>
Yönetilen olay işleyicisi yönteminin, gibi ilk bağımsız değişkeni `Object^` .

*ARG1*<br/>
Yönetilen olay işleyicisi yönteminin, gibi ikinci bağımsız değişkeni `EventArgs^` .

### <a name="remarks"></a>Açıklamalar

Temsilci eşlemesindeki her giriş, [MAKE_DELEGATE](#make_delegate)tarafından oluşturulan bir yönetilen olay işleyicisi temsilcisine karşılık gelir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, olay işleyicisi için temsilci eşlemesinde bir giriş oluşturmak üzere EVENT_DELEGATE_ENTRY nasıl kullanılacağını gösterir `OnClick` ; Ayrıca, MAKE_DELEGATE kod örneğine bakın. Daha fazla bilgi için bkz. [nasıl yapılır: Yerel C++ sınıflarından Windows Forms olaylarını havuza](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)alma.

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** msclr\event.h

## <a name="interface_part"></a><a name="interface_part"></a> INTERFACE_PART

Nesnenizin destekleyeceği her arabirim için BEGIN_INTERFACE_MAP makrosu ve END_INTERFACE_MAP makrosu arasında kullanılır.

### <a name="syntax"></a>Sözdizimi

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Arabirim eşlemesini içeren sınıfın adı.
*'si*<br/>
Katıştırılmış sınıfa eşlenecek IID.
*localClass*<br/>
Yerel sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Bir IID *'yi, sınıfsınıfı ve* *localClass* tarafından belirtilen sınıfın bir üyesine eşlemenizi sağlar.

Arabirim haritaları hakkında daha fazla bilgi için bkz. [teknik notta 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="make_delegate"></a><a name="make_delegate"></a> MAKE_DELEGATE

Yönetilen denetime bir olay işleyicisi ekler.

### <a name="syntax"></a>Sözdizimi

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>Parametreler

*ĞINI*<br/>
[EventHandler](/dotnet/api/system.eventhandler)gibi, yönetilen olay işleyicisi temsilcisinin türü.

*ÜYESIDIR*<br/>
Denetime eklenecek olay işleyicisi yönteminin adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, *temsilci* türünde ve ad *üyesinin* yönetilen bir olay işleyicisi temsilcisi oluşturur. Yönetilen olay işleyicisi temsilcisi, yerel bir sınıfın yönetilen olayları işlemesini sağlar.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `MAKE_DELEGATE` `OnClick` bir MFC denetimine bir olay işleyicisi iliştirmek için nasıl çağrılacağını gösterir `MyControl` . Bu makronun bir MFC uygulamasında nasıl çalıştığı hakkında daha geniş bir açıklama için bkz. [nasıl yapılır: Yerel C++ sınıflarından Windows Forms olaylarını havuza](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)alma.

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

[Nasıl yapılır: Yerel C++ Sınıflarından Windows Forms olaylarını havuza alma](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[Nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
