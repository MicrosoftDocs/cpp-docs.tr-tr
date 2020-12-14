---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: genel bir özel durum Işleyicisi tanımlama ve yüklemeyi'
title: 'Nasıl yapılır: Genel Bir Özel Durum İşleyicisi Tanımlama ve Yükleme'
ms.date: 11/04/2016
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
ms.openlocfilehash: 6747e0bdf95ae4d87ed667576852c282e05a7d6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258346"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>Nasıl yapılır: Genel Bir Özel Durum İşleyicisi Tanımlama ve Yükleme

Aşağıdaki kod örneği, işlenmemiş özel durumların nasıl yakalanabileceğini gösterir. Örnek form, basıldığında bir özel durum oluşturulması için bir null başvurusu gerçekleştirdiğinde bir düğme içerir. Bu işlev tipik bir kod hatasını temsil eder. Elde edilen özel durum, ana işlev tarafından yüklenen uygulama genelinde özel durum işleyicisi tarafından yakalanır.

Bu, olaya bir temsilci bağlayarak yapılır <xref:System.Windows.Forms.Application.ThreadException> . Bu durumda, sonraki özel durumlar `App::OnUnhandled` yöntemine gönderilir.

## <a name="example"></a>Örnek

```cpp
// global_exception_handler.cpp
// compile with: /clr
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Drawing;
using namespace System::Windows::Forms;

ref class MyForm : public Form
{
   Button^ b;
public:
   MyForm( )
   {
      b = gcnew Button( );
      b->Text = "Do Null Access";
      b->Size = Drawing::Size(150, 30);
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);
      Controls->Add(b);
   }
   void OnClick(Object^ sender, EventArgs^ args)
   {
      // do something illegal, like call through a null pointer...
      Object^ o = nullptr;
      o->ToString( );
   }
};

ref class App
{
public:
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)
   {
      MessageBox::Show(e->Exception->Message, "Global Exeception");
      Application::ExitThread( );
   }
};

int main()
{
   Application::ThreadException += gcnew
      ThreadExceptionEventHandler(App::OnUnhandled);

   MyForm^ form = gcnew MyForm( );
   Application::Run(form);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../extensions/exception-handling-cpp-component-extensions.md)
