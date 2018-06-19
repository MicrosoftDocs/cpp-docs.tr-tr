---
title: Bir eklenti mimarisi uygulama (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- plug-ins [C++]
- reflection [C++}, plug-ins
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4e001ef88af0727a994c309d45167787d3e6677b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135219"
---
# <a name="how-to-implement-a-plug-in-component-architecture-using-reflection-ccli"></a>Nasıl yapılır: Yansıma Kullanarak Eklenti Bileşeni Mimarisi Uygulama (C++/CLI)
Aşağıdaki kod örnekleri, basit bir "eklenti" mimarisi uygulamada yansıma kullanımını gösterir. İlk liste uygulamadır ve ikincisi ise eklentidir. Uygulama kendisini komut satırı bağımsız değişkeni olarak sağlanan eklentisi DLL'sini bulunan herhangi bir form tabanlı sınıflarını kullanarak dolduran bir birden çok belge biçimidir.  
  
 Uygulama kullanarak sağlanan derlemeyi yüklemeye çalışır <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> yöntemi. Başarılı derleme içindeki türler kullanılarak numaralandırılır varsa <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> yöntemi. Uyumluluk kullanarak her tür denetlenir <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> yöntemi. Bu örnekte, sağlanan derlemesinde türetilmiş sınıflar gereken <xref:System.Windows.Forms.Form> bir eklenti nitelemek için sınıf.  
  
 Uyumlu sınıfların ait sonra ile örneklerin <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> kabul yöntemi bir <xref:System.Type> bağımsız değişken olarak ve yeni bir örneği için bir işaretçi döndürür. Her yeni örnek daha sonra forma eklenir ve görüntülenir.  
  
 Unutmayın <xref:System.Reflection.Assembly.Load%2A> yöntemi dosya uzantısını içeren derleme adları kabul etmiyor. Uygulama main işlevi herhangi sağlanan uzantıları kırpar, böylece her iki durumda da aşağıdaki kod örneğinde çalışır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod eklentileri kabul eden uygulama tanımlar. İlk bağımsız değişkeni olarak bir derleme adı sağlanmalıdır. Bu derleme en az bir ortak içermelidir <xref:System.Windows.Forms.Form> türetilmiş türü.  
  
```  
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod türetilen üç sınıf tanımlar <xref:System.Windows.Forms.Form>. Sonuçta elde edilen derleme adı, önceki listede bulunan yürütülebilir geçirildiğinde üç bu sınıfların her biri öğeleri bulunacak ve derleme zamanında barındırma uygulama için tüm bilinmeyen olgusuna karşın örneği.  
  
```  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)