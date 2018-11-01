---
title: Windows İşlemleri (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows [C++], Windows-specific tasks
- .NET Framework [C++], Windows operations
- Visual C++, Windows operations
- Windows operations [C++]
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
- Visual C++, user interactive state
- user interactive state
- Visual C++, reading from Windows Registry
- registry, reading
- performance counters
- performance counters, reading Windows performance counters
- performance monitoring, Windows performance counters
- performance, counters
- counters, reading Windows performance counters
- performance
- performance monitoring
- text, retrieving from Clipboard
- Clipboard, retrieving text
- current user names
- user names, retrieving
- UserName string
- .NET Framework, version
- Version property, retrieving .NET Framework version
- computer name, retrieving
- machine name, retrieving
- computer name
- Windows [C++], version
- Windows [C++], retrieving version using Visual C++
- time, elapsed since startup
- counters, elapsed time
- startup, time elapsed since
- tick counts
- startup
- text, storing in Clipboard
- Clipboard, storing text
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: b9a75cb4-0589-4d5b-92cb-5e8be42b4ac0
ms.openlocfilehash: d23eef1d48674751a725e076d1b652b304ad40a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508400"
---
# <a name="windows-operations-ccli"></a>Windows İşlemleri (C++/CLI)

Windows SDK'sını kullanarak Windows özgü çeşitli görevleri gösterir.

Aşağıdaki konular Windows Visual C++ kullanarak SDK ile gerçekleştirilen çeşitli Windows işlemlerini gösterir.

## <a name="determine_shutdown"></a> Kapatmanın başlayıp başlamadığını belirleme

Aşağıdaki kod örneği, uygulamanın veya .NET Framework şu anda sonlandırıyor olup olmadığını belirlemek nasıl gösterir. Bu, .NET Framework'teki statik öğeler bu yapıları kapatma sırasında sistem tarafından kesin ve güvenilir bir şekilde kullanılamaz çünkü erişmek için kullanışlıdır. Denetleyerek <xref:System.Environment.HasShutdownStarted%2A> özelliği ilk olarak, bu öğeleri erişilmemesi olası hataları önleyebilirsiniz.

### <a name="example"></a>Örnek

```cpp
// check_shutdown.cpp
// compile with: /clr
using namespace System;
int main()
{
   if (Environment::HasShutdownStarted)
      Console::WriteLine("Shutting down.");
   else
      Console::WriteLine("Not shutting down.");
   return 0;
}
```

## <a name="determine_user"></a> Kullanıcı etkileşimli durumunu belirleme

Aşağıdaki kod örneği, kodu kullanıcı etkileşimli bir bağlamda çalıştırıldığını olmadığının nasıl gösterir. Varsa <xref:System.Environment.UserInteractive%2A> false ise, kodu bir hizmet işlemi olarak çalışıyor veya gelen içinde bir Web uygulaması, bu durumda, kullanıcı ile etkileşim kurmak kullanmamanız gerekir.

### <a name="example"></a>Örnek

```cpp
// user_interactive.cpp
// compile with: /clr
using namespace System;

int main()
{
   if ( Environment::UserInteractive )
      Console::WriteLine("User interactive");
   else
      Console::WriteLine("Noninteractive");
   return 0;
}
```

## <a name="read_registry"></a> Windows kayıt defterinden veri okuma

Aşağıdaki kod örneğinde <xref:Microsoft.Win32.Registry.CurrentUser> anahtarını Windows kayıt defterinden veri okuma için. İlk olarak, anahtarlar kullanılarak numaralandırılır <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> yöntemi ve kimliklerini alt açıldığında kullanarak <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> yöntemi. Kök anahtarları gibi her alt tarafından temsil edilen <xref:Microsoft.Win32.RegistryKey> sınıfı. Son olarak, yeni <xref:Microsoft.Win32.RegistryKey> nesne, anahtar/değer çiftleri listeleme için kullanılır.

### <a name="example"></a>Örnek

```cpp
// registry_read.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main( )
{
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );

   Console::WriteLine("Subkeys within CurrentUser root key:");
   for (int i=0; i<key->Length; i++)
   {
      Console::WriteLine("   {0}", key[i]);
   }

   Console::WriteLine("Opening subkey 'Identities'...");
   RegistryKey^ rk = nullptr;
   rk = Registry::CurrentUser->OpenSubKey("Identities");
   if (rk==nullptr)
   {
      Console::WriteLine("Registry key not found - aborting");
      return -1;
   }

   Console::WriteLine("Key/value pairs within 'Identities' key:");
   array<String^>^ name = rk->GetValueNames( );
   for (int i=0; i<name->Length; i++)
   {
      String^ value = rk->GetValue(name[i])->ToString();
      Console::WriteLine("   {0} = {1}", name[i], value);
   }

   return 0;
}
```

### <a name="remarks"></a>Açıklamalar

<xref:Microsoft.Win32.Registry> Sınıfı, yalnızca statik örnekleri için bir kapsayıcı <xref:Microsoft.Win32.RegistryKey>. Her örnek, bir kök kayıt defteri düğümü temsil eder. Örnekleri <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, ve <xref:Microsoft.Win32.Registry.Users>.

Olmanın yanı sıra statik içindeki nesneleri <xref:Microsoft.Win32.Registry> sınıfı salt okunurdur. Ayrıca, örnekler, <xref:Microsoft.Win32.RegistryKey> kayıt içeriğine erişmek için oluşturulan sınıf nesneleri salt okunurdur de. Bu davranışı geçersiz kılmak nasıl bir örnek için bkz [nasıl yapılır: Windows kayıt defterine veri yazma (C + +/ CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).

İki ek nesnesi vardır <xref:Microsoft.Win32.Registry> sınıfı: <xref:Microsoft.Win32.Registry.DynData> ve <xref:Microsoft.Win32.Registry.PerformanceData>. Her ikisi de örnekleridir <xref:Microsoft.Win32.RegistryKey> sınıfı. <xref:Microsoft.Win32.Registry.DynData> Nesnesi yalnızca Windows 98 ve Windows Me desteklenmeyen dinamik kayıt defteri bilgileri içerir <xref:Microsoft.Win32.Registry.PerformanceData> Nesnesini Windows performans izleme sistemi kullanan uygulamalar için performans sayacı bilgileri erişmek için kullanılabilir. <xref:Microsoft.Win32.Registry.PerformanceData> Düğümü gerçekten kayıt defterinde depolanır ve bu nedenle Regedit.exe kullanarak görüntülenemiyor bilgileri temsil eder.

## <a name="read_performance"></a> Windows performans sayaçlarını okuma

Bazı uygulamalar ve Windows alt sistemlerin performans verileri Windows Performans sistemi aracılığıyla kullanıma sunar. Bu sayaçlardan kullanılarak erişilebilir <xref:System.Diagnostics.PerformanceCounterCategory> ve <xref:System.Diagnostics.PerformanceCounter> bulunan sınıfları <xref:System.Diagnostics?displayProperty=fullName> ad alanı.

Aşağıdaki kod örneği bu sınıfları almak ve görüntülemek işlemcinin meşgul olduğu sürenin yüzdesini belirtmek için Windows tarafından güncelleştirilmiş bir sayaç için kullanır.

> [!NOTE]
>  Bu örnek, Windows Vista üzerinde çalıştırmak için yönetici ayrıcalıkları gerektirir.

### <a name="example"></a>Örnek

```cpp
// processor_timer.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Diagnostics;
using namespace System::Timers;

ref struct TimerObject
{
public:
   static String^ m_instanceName;
   static PerformanceCounter^ m_theCounter;

public:
   static void OnTimer(Object^ source, ElapsedEventArgs^ e)
   {
      try
      {
         Console::WriteLine("CPU time used: {0,6} ",
          m_theCounter->NextValue( ).ToString("f"));
      }
      catch(Exception^ e)
      {
         if (dynamic_cast<InvalidOperationException^>(e))
         {
            Console::WriteLine("Instance '{0}' does not exist",
                  m_instanceName);
            return;
         }
         else
         {
            Console::WriteLine("Unknown exception... ('q' to quit)");
            return;
         }
      }
   }
};

int main()
{
   String^ objectName = "Processor";
   String^ counterName = "% Processor Time";
   String^ instanceName = "_Total";

   try
   {
      if ( !PerformanceCounterCategory::Exists(objectName) )
      {
         Console::WriteLine("Object {0} does not exist", objectName);
         return -1;
      }
   }
   catch (UnauthorizedAccessException ^ex)
   {
      Console::WriteLine("You are not authorized to access this information.");
      Console::Write("If you are using Windows Vista, run the application with ");
      Console::WriteLine("administrative privileges.");
      Console::WriteLine(ex->Message);
      return -1;
   }

   if ( !PerformanceCounterCategory::CounterExists(
          counterName, objectName) )
   {
      Console::WriteLine("Counter {0} does not exist", counterName);
      return -1;
   }

   TimerObject::m_instanceName = instanceName;
   TimerObject::m_theCounter = gcnew PerformanceCounter(
          objectName, counterName, instanceName);

   System::Timers::Timer^ aTimer = gcnew System::Timers::Timer();
   aTimer->Elapsed += gcnew ElapsedEventHandler(&TimerObject::OnTimer);
   aTimer->Interval = 1000;
   aTimer->Enabled = true;
   aTimer->AutoReset = true;

   Console::WriteLine("reporting CPU usage for the next 10 seconds");
   Thread::Sleep(10000);
   return 0;
}
```

## <a name="retrieve_text"></a> Panodan Metin Alma

Aşağıdaki kod örneğinde <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> üye işlevi işaretçisi döndürülecek <xref:System.Windows.Forms.IDataObject> arabirimi. Bu arabirim için verilerin biçimi sorgulanabilir ve gerçek veri almak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// read_clipboard.cpp
// compile with: /clr
#using <system.dll>
#using <system.Drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main( )
{
   IDataObject^ data = Clipboard::GetDataObject( );

   if (data)
   {
      if (data->GetDataPresent(DataFormats::Text))
      {
         String^ text = static_cast<String^>
           (data->GetData(DataFormats::Text));
         Console::WriteLine(text);
      }
      else
         Console::WriteLine("Nontext data is in the Clipboard.");
   }
   else
   {
      Console::WriteLine("No data was found in the Clipboard.");
   }

   return 0;
}
```

## <a name="retrieve_current"></a> Geçerli kullanıcı adını alma

Aşağıdaki kod örneği, geçerli kullanıcı adını (Windows açmış olan kullanıcının adını) alma gösterir. Ad içinde depolanan <xref:System.Environment.UserName%2A> tanımlanan dize <xref:System.Environment> ad alanı.

### <a name="example"></a>Örnek

```cpp
// username.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);
   return 0;
}
```

## <a name="retrieve_dotnet"></a> .NET Framework sürümünü alma

Aşağıdaki kod örneği ile şu anda yüklü olan .NET Framework sürümünü belirlemek gösterilmiştir <xref:System.Environment.Version%2A> bir işaretçi olan bir özellik için bir <xref:System.Version> sürüm bilgisi içeren nesne.

### <a name="example"></a>Örnek

```cpp
// dotnet_ver.cpp
// compile with: /clr
using namespace System;
int main()
{
   Version^ version = Environment::Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write(".NET Framework version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
            build, major, minor, revision);
   }
   return 0;
}
```

## <a name="retrieve_local"></a> Yerel makine adını alma

Aşağıdaki kod örneğinde yerel makine adını alma gösterir (gibi bilgisayar adını, ağ üzerinde görünür). Bunu alarak gerçekleştirmek <xref:System.Environment.MachineName%2A> tanımlanan dize <xref:System.Environment> ad alanı.

### <a name="example"></a>Örnek

```cpp
// machine_name.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);
   return 0;
}
```

## <a name="retrieve_version"></a> Windows sürümünü alma

Aşağıdaki kod örneği, geçerli işletim sistemi platformu ve sürüm bilgilerini almak nasıl gösterir. Bu bilgiler saklanır <xref:System.Environment.OSVersion%2A?displayProperty=fullName> özelliği ve ayrıntılı koşullarla Windows sürümünü tanımlayan bir numaralandırma oluşur ve <xref:System.Environment.Version%2A> işletim sisteminin tam derleme içeren nesne.

### <a name="example"></a>Örnek

```cpp
// os_ver.cpp
// compile with: /clr
using namespace System;

int main()
{
   OperatingSystem^ osv = Environment::OSVersion;
   PlatformID id = osv->Platform;
   Console::Write("Operating system: ");

   if (id == PlatformID::Win32NT)
      Console::WriteLine("Win32NT");
   else if (id == PlatformID::Win32S)
      Console::WriteLine("Win32S");
   else if (id == PlatformID::Win32Windows)
      Console::WriteLine("Win32Windows");
   else
      Console::WriteLine("WinCE");

   Version^ version = osv->Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write("OS Version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
                   build, major, minor, revision);
   }

   return 0;
}
```

## <a name="retrieve_time"></a> Başlangıçtan itibaren geçen zamanı alma

Aşağıdaki kod örneği, işaret sayısını belirlemek gösterilmiştir veya Windows beri geçen milisaniye sayısını başlatıldı. Bu değer depolanan <xref:System.Environment.TickCount%2A?displayProperty=fullName> üyesi ve 32-bit bir değer olduğundan, 24,9 günde yaklaşık olarak sıfırlar.

### <a name="example"></a>Örnek

```cpp
// startup_time.cpp
// compile with: /clr
using namespace System;

int main( )
{
   Int32 tc = Environment::TickCount;
   Int32 seconds = tc / 1000;
   Int32 minutes = seconds / 60;
   float hours = static_cast<float>(minutes) / 60;
   float days = hours / 24;

   Console::WriteLine("Milliseconds since startup: {0}", tc);
   Console::WriteLine("Seconds since startup: {0}", seconds);
   Console::WriteLine("Minutes since startup: {0}", minutes);
   Console::WriteLine("Hours since startup: {0}", hours);
   Console::WriteLine("Days since startup: {0}", days);

   return 0;
}
```

## <a name="store_text"></a> Metin panoya Store

Aşağıdaki kod örneğinde <xref:System.Windows.Forms.Clipboard> içinde tanımlanan nesne <xref:System.Windows.Forms> bir dize depolamak için ad alanı. Bu nesne iki üye işlevleri sağlar: <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> ve <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. Verileri panoya türetilen herhangi bir nesnenin göndererek depolandığı <xref:System.Object> için <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.

### <a name="example"></a>Örnek

```cpp
// store_clipboard.cpp
// compile with: /clr
#using <System.dll>
#using <System.Drawing.dll>
#using <System.Windows.Forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main()
{
   String^ str = "This text is copied into the Clipboard.";

   // Use 'true' as the second argument if
   // the data is to remain in the clipboard
   // after the program terminates.
   Clipboard::SetDataObject(str, true);

   Console::WriteLine("Added text to the Clipboard.");

   return 0;
}
```

## <a name="write_data"></a> Windows kayıt defterine veri yazma

Aşağıdaki kod örneğinde <xref:Microsoft.Win32.Registry.CurrentUser> yazılabilir bir örneğini oluşturmak için anahtar <xref:Microsoft.Win32.RegistryKey> sınıfı karşılık gelen **yazılım** anahtarı. <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> Yöntemi ardından yeni bir anahtar oluşturun ve anahtar/değer çiftlerini eklemek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// registry_write.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main()
{
   // The second OpenSubKey argument indicates that
   // the subkey should be writable.
   RegistryKey^ rk;
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);
   if (!rk)
   {
      Console::WriteLine("Failed to open CurrentUser/Software key");
      return -1;
   }

   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");
   if (!nk)
   {
      Console::WriteLine("Failed to create 'NewRegKey'");
      return -1;
   }

   String^ newValue = "NewValue";
   try
   {
      nk->SetValue("NewKey", newValue);
      nk->SetValue("NewKey2", 44);
   }
   catch (Exception^)
   {
      Console::WriteLine("Failed to set new values in 'NewRegKey'");
      return -1;
   }

   Console::WriteLine("New key created.");
   Console::Write("Use REGEDIT.EXE to verify ");
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");
   return 0;
}
```

### <a name="remarks"></a>Açıklamalar

.NET Framework ile kayıt defterine erişmek için kullanabileceğiniz <xref:Microsoft.Win32.Registry> ve [RegistryKey](https://msdn.microsoft.com/library/microsoft.win32.registrykey.aspx) her ikisi de sınıfları tanımlanan <xref:Microsoft.Win32> ad alanı. **Kayıt defteri** sınıfı statik örnekleri için bir kapsayıcıdır <xref:Microsoft.Win32.RegistryKey> sınıfı. Her örnek, bir kök kayıt defteri düğümü temsil eder. Örnekleri <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, ve <xref:Microsoft.Win32.Registry.Users>.

## <a name="related-sections"></a>İlgili Bölümler

<xref:System.Environment>

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
