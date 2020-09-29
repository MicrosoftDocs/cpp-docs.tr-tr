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
ms.openlocfilehash: 3c4ef2a69c25313ff444e0fabaea6eef2feeeee2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501660"
---
# <a name="windows-operations-ccli"></a>Windows İşlemleri (C++/CLI)

Windows SDK kullanarak Windows 'a özgü çeşitli görevleri gösterir.

Aşağıdaki konularda Visual C++ kullanılarak Windows SDK gerçekleştirilen çeşitli Windows işlemleri gösterilmektedir.

## <a name="determine-if-shutdown-has-started"></a><a name="determine_shutdown"></a> Kapatılma işleminin başlatılıp başlatılmadığını belirleme

Aşağıdaki kod örneği, uygulamanın veya .NET Framework şu anda sonlandırıp kalmadığını nasıl belirleyebileceğinizi gösterir. Bu, kapatılırken statik .NET Framework öğelere erişmek için yararlıdır, çünkü bu yapılar sistem tarafından sonlandırılır ve güvenilir bir şekilde kullanılamaz. <xref:System.Environment.HasShutdownStarted%2A>Önce özelliği denetleyerek, bu öğelere erişmemek için olası hatalardan kaçınabilirsiniz.

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

## <a name="determine-the-user-interactive-state"></a><a name="determine_user"></a> Kullanıcı etkileşimli durumunu belirleme

Aşağıdaki kod örneği, kodun kullanıcı etkileşimli bir bağlamda çalıştırılıp çalıştırılmadığını nasıl belirleyebileceğinizi gösterir. <xref:System.Environment.UserInteractive%2A>Yanlış ise, kod bir hizmet işlemi olarak veya bir Web uygulamasının içinden çalışıyor, bu durumda kullanıcıyla etkileşime geçme denemeniz gerekir.

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

## <a name="read-data-from-the-windows-registry"></a><a name="read_registry"></a> Windows kayıt defterinden veri okuma

Aşağıdaki kod örneği, <xref:Microsoft.Win32.Registry.CurrentUser> Windows kayıt defterinden verileri okumak için anahtarını kullanır. İlk olarak, anahtar anahtarlar yöntemi kullanılarak numaralandırılır <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> ve sonra kimlikler alt anahtarı yöntemi kullanılarak açılır <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> . Kök anahtarlar gibi her alt anahtar de sınıf tarafından temsil edilir <xref:Microsoft.Win32.RegistryKey> . Son olarak, yeni <xref:Microsoft.Win32.RegistryKey> nesne, anahtar/değer çiftlerini listelemek için kullanılır.

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

<xref:Microsoft.Win32.Registry>Sınıfı yalnızca statik örnekleri için bir kapsayıcıdır <xref:Microsoft.Win32.RegistryKey> . Her örnek bir kök kayıt defteri düğümünü temsil eder. Örnekler,, <xref:Microsoft.Win32.Registry.ClassesRoot> , <xref:Microsoft.Win32.Registry.CurrentConfig> <xref:Microsoft.Win32.Registry.CurrentUser> <xref:Microsoft.Win32.Registry.LocalMachine> ve <xref:Microsoft.Win32.Registry.Users> .

Statik olmanın yanı sıra, sınıf içindeki nesneler <xref:Microsoft.Win32.Registry> salt okunurdur. Ayrıca, <xref:Microsoft.Win32.RegistryKey> kayıt defteri nesnelerinin içeriğine erişmek için oluşturulan sınıf örnekleri de salt okunurdur. Bu davranışı geçersiz kılma hakkında bir örnek için bkz. [nasıl yapılır: Windows kayıt defterine veri yazma (C++/CLI)](#write_data).

Sınıfında iki ek nesne vardır <xref:Microsoft.Win32.Registry> : <xref:Microsoft.Win32.Registry.DynData> ve <xref:Microsoft.Win32.Registry.PerformanceData> . Her ikisi de sınıfının örnekleridir <xref:Microsoft.Win32.RegistryKey> . <xref:Microsoft.Win32.Registry.DynData>Nesne, yalnızca windows 98 ve Windows Me 'de desteklenen dinamik kayıt defteri bilgilerini içerir. <xref:Microsoft.Win32.Registry.PerformanceData>Nesnesi, Windows performans Izleme sistemini kullanan uygulamalar için performans sayacı bilgilerine erişmek için kullanılabilir. <xref:Microsoft.Win32.Registry.PerformanceData>Düğüm, aslında kayıt defterinde depolanmayan bilgileri temsil eder ve bu nedenle Regedit.exe kullanılarak görüntülenemez.

## <a name="read-windows-performance-counters"></a><a name="read_performance"></a> Windows performans sayaçlarını okuma

Bazı uygulamalar ve Windows alt sistemleri, performans verilerini Windows performans sistemi üzerinden kullanıma sunar. Bu sayaçlara, <xref:System.Diagnostics.PerformanceCounterCategory> <xref:System.Diagnostics.PerformanceCounter> ad alanında bulunan ve sınıfları kullanılarak erişilebilir <xref:System.Diagnostics?displayProperty=fullName> .

Aşağıdaki kod örneği, işlemcinin meşgul olduğu sürenin yüzdesini göstermek için Windows tarafından güncelleştirilmiş bir sayacı almak ve göstermek üzere bu sınıfları kullanır.

> [!NOTE]
> Bu örnek, Windows Vista 'da çalıştırmak için yönetici ayrıcalıkları gerektirir.

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

## <a name="retrieve-text-from-the-clipboard"></a><a name="retrieve_text"></a> Panodan metin alma

Aşağıdaki kod örneği, <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> arabirimine bir işaretçi döndürmek için üye işlevini kullanır <xref:System.Windows.Forms.IDataObject> . Bu arabirim daha sonra verilerin biçimi için sorgulanabilir ve gerçek verileri almak için kullanılır.

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

## <a name="retrieve-the-current-username"></a><a name="retrieve_current"></a> Geçerli Kullanıcı adını alma

Aşağıdaki kod örneği, geçerli kullanıcı adının (Windows 'da oturum açan kullanıcının adı) alınmasını gösterir. Ad, <xref:System.Environment.UserName%2A> ad alanında tanımlanan, dizesinde saklanır <xref:System.Environment> .

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

## <a name="retrieve-the-net-framework-version"></a><a name="retrieve_dotnet"></a> .NET Framework sürümünü alma

Aşağıdaki kod örneği, <xref:System.Environment.Version%2A> sürüm bilgilerini içeren bir nesnenin işaretçisi olan özelliği ile Şu anda yüklü .NET Framework sürümünün nasıl belirleneceğini göstermektedir <xref:System.Version> .

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

## <a name="retrieve-the-local-machine-name"></a><a name="retrieve_local"></a> Yerel makine adını alma

Aşağıdaki kod örneğinde, yerel makine adının (bir ağda göründüğü haliyle bilgisayarın adı) alınması gösterilmektedir. Bunu <xref:System.Environment.MachineName%2A> , ad alanında tanımlanan dizeyi alarak yapabilirsiniz <xref:System.Environment> .

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

## <a name="retrieve-the-windows-version"></a><a name="retrieve_version"></a> Windows sürümünü al

Aşağıdaki kod örneği, geçerli işletim sisteminin platform ve sürüm bilgilerinin nasıl alınacağını gösterir. Bu bilgiler, <xref:System.Environment.OSVersion%2A?displayProperty=fullName> özelliğinde depolanır ve Windows 'un, geniş şartlar halinde ve <xref:System.Environment.Version%2A> işletim sisteminin tam derlemesini içeren bir nesne sürümünü açıklayan bir sabit listesi içerir.

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

## <a name="retrieve-time-elapsed-since-startup"></a><a name="retrieve_time"></a> Başlangıçtan Itibaren geçen süreyi al

Aşağıdaki kod örneği, Windows 'un başlatılmasından bu yana geçen değer sayısını veya milisaniye sayısını nasıl belirleyebileceğinizi gösterir. Bu değer, <xref:System.Environment.TickCount%2A?displayProperty=fullName> üyede depolanır ve 32 bitlik bir değer olduğundan, yaklaşık olarak her 24,9 günde bir sıfıra sıfırlanır.

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

## <a name="store-text-in-the-clipboard"></a><a name="store_text"></a> Metni panoda depola

Aşağıdaki kod örneği, <xref:System.Windows.Forms.Clipboard> <xref:System.Windows.Forms> bir dizeyi depolamak için ad alanında tanımlanan nesnesini kullanır. Bu nesne iki üye işlevi sağlar: <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> ve <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> . Veriler, ' dan türetilmiş herhangi bir nesne gönderilerek Pano 'da depolanır <xref:System.Object> <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> .

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

## <a name="write-data-to-the-windows-registry"></a><a name="write_data"></a> Windows kayıt defterine veri yazma

Aşağıdaki kod örneği, <xref:Microsoft.Win32.Registry.CurrentUser> <xref:Microsoft.Win32.RegistryKey> **yazılım** anahtarına karşılık gelen sınıfının yazılabilir bir örneğini oluşturmak için anahtarını kullanır. <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>Daha sonra yöntemi yeni bir anahtar oluşturmak ve anahtar/değer çiftlerine eklemek için kullanılır.

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

<xref:Microsoft.Win32.Registry> <xref:Microsoft.Win32.RegistryKey> Her ikisi de ad alanında tanımlanan ve sınıflarıyla kayıt defterine erişmek için .NET Framework kullanabilirsiniz <xref:Microsoft.Win32> . **Kayıt defteri** sınıfı, sınıfının statik örnekleri için bir kapsayıcıdır <xref:Microsoft.Win32.RegistryKey> . Her örnek bir kök kayıt defteri düğümünü temsil eder. Örnekler,, <xref:Microsoft.Win32.Registry.ClassesRoot> , <xref:Microsoft.Win32.Registry.CurrentConfig> <xref:Microsoft.Win32.Registry.CurrentUser> <xref:Microsoft.Win32.Registry.LocalMachine> ve <xref:Microsoft.Win32.Registry.Users> .

## <a name="related-sections"></a>İlgili Bölümler

<xref:System.Environment>

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
