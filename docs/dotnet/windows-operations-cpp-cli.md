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
ms.openlocfilehash: 99fce804ad30e01bdbaa99b1636a5238ff535f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371766"
---
# <a name="windows-operations-ccli"></a>Windows İşlemleri (C++/CLI)

Windows SDK'yı kullanarak Windows'a özgü çeşitli görevleri gösterir.

Aşağıdaki konular, Visual C++'ı kullanarak Windows SDK ile gerçekleştirilen çeşitli Windows işlemlerini göstermektedir.

## <a name="determine-if-shutdown-has-started"></a><a name="determine_shutdown"></a>KapatmaNın Başlatıp Başlad'ı Olup Olmadığını Belirleme

Aşağıdaki kod örneği, uygulamanın veya .NET Çerçevesinin şu anda sonlandırma olup olmadığının nasıl belirlendiğini gösterir. Bu, .NET Framework'deki statik öğelere erişmek için yararlıdır, çünkü kapatma sırasında bu yapılar sistem tarafından sonuçlandırılır ve güvenilir bir şekilde kullanılamaz. Önce <xref:System.Environment.HasShutdownStarted%2A> özelliği denetleyerek, bu öğelere erişmeyerak olası hataları önleyebilirsiniz.

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

## <a name="determine-the-user-interactive-state"></a><a name="determine_user"></a>Kullanıcı Etkileşimli Durumunu Belirleme

Aşağıdaki kod örneği, kodun kullanıcı etkileşimli bir bağlamda çalıştırılıp çalıştırılmadığının nasıl belirlendiğini gösterir. Yanlışsa, <xref:System.Environment.UserInteractive%2A> kod bir hizmet işlemi olarak veya bir Web uygulamasının içinden çalışıyor, bu durumda kullanıcıyla etkileşimkurmaya çalışmamalısınız.

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

## <a name="read-data-from-the-windows-registry"></a><a name="read_registry"></a>Windows Kayıt Defteri'nden Verileri Okuma

Aşağıdaki kod örneği, <xref:Microsoft.Win32.Registry.CurrentUser> Windows kayıt defterindeki verileri okumak için anahtarı kullanır. Önce alt tuşlar <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> yöntem kullanılarak numaralandırılır ve daha sonra Kimlikler alt <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> anahtarı yöntem kullanılarak açılır. Kök anahtarlar gibi, her alt anahtar <xref:Microsoft.Win32.RegistryKey> sınıf tarafından temsil edilir. Son olarak, <xref:Microsoft.Win32.RegistryKey> yeni nesne anahtar/değer çiftlerini sayısallandırmak için kullanılır.

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

Sınıf, <xref:Microsoft.Win32.Registry> statik örnekleri için yalnızca <xref:Microsoft.Win32.RegistryKey>bir kapsayıcıdır. Her örnek bir kök kayıt defteri düğümünü temsil eder. Örnekler <xref:Microsoft.Win32.Registry.ClassesRoot>, , <xref:Microsoft.Win32.Registry.CurrentConfig> <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, <xref:Microsoft.Win32.Registry.Users>ve .

Statik olmanın yanı sıra, <xref:Microsoft.Win32.Registry> sınıf içindeki nesneler salt okunur. Ayrıca, kayıt defteri <xref:Microsoft.Win32.RegistryKey> nesnelerinin içeriğine erişmek için oluşturulan sınıfın örnekleri de salt okunur. Bu davranışı nasıl geçersiz kılabilirsiniz bir örnek için [bkz: Windows Kayıt Defterine Veri Yazma (C++/CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).

<xref:Microsoft.Win32.Registry> Sınıfta iki ek nesne vardır: <xref:Microsoft.Win32.Registry.DynData> <xref:Microsoft.Win32.Registry.PerformanceData>ve . Her ikisi de <xref:Microsoft.Win32.RegistryKey> sınıfın örnekleridir. Nesne, <xref:Microsoft.Win32.Registry.DynData> yalnızca Windows 98 ve Windows Me'de desteklenen dinamik kayıt defteri bilgileri içerir. Nesne, <xref:Microsoft.Win32.Registry.PerformanceData> Windows Performans İzleme Sistemi'ni kullanan uygulamaların performans sayacı bilgilerine erişmek için kullanılabilir. Düğüm, <xref:Microsoft.Win32.Registry.PerformanceData> kayıt defterinde gerçekte depolanamayan ve bu nedenle Regedit.exe kullanılarak görüntülenemeyen bilgileri temsil eder.

## <a name="read-windows-performance-counters"></a><a name="read_performance"></a>Windows Performans Sayaçlarını Okuma

Bazı uygulamalar ve Windows alt sistemleri, Windows performans sistemi aracılığıyla performans verilerini ortaya çıkarır. Bu sayaçlara <xref:System.Diagnostics.PerformanceCounterCategory> <xref:System.Diagnostics.PerformanceCounter> <xref:System.Diagnostics?displayProperty=fullName> ad alanında bulunan ve sınıfları kullanılarak erişilebilir.

Aşağıdaki kod örneği, işlemcinin meşgul olduğu süre yüzdesini belirtmek için Windows tarafından güncelleştirilen bir sayacı almak ve görüntülemek için bu sınıfları kullanır.

> [!NOTE]
> Bu örnek, Windows Vista'da çalıştırmak için yönetim ayrıcalıkları gerektirir.

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

## <a name="retrieve-text-from-the-clipboard"></a><a name="retrieve_text"></a>Panodan Metin Alma

Aşağıdaki kod örneği, <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> bir işaretçiyi <xref:System.Windows.Forms.IDataObject> arabirime döndürmek için üye işlevi kullanır. Bu arabirim daha sonra verilerin biçimi için sorgulanabilir ve gerçek verileri almak için kullanılabilir.

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

## <a name="retrieve-the-current-username"></a><a name="retrieve_current"></a>Geçerli Kullanıcı Adını Alma

Aşağıdaki kod örneği, geçerli kullanıcı adının (Windows'a giriş yapılan kullanıcının adı) alınmasını gösterir. Ad, <xref:System.Environment> ad alanında <xref:System.Environment.UserName%2A> tanımlanan dizede depolanır.

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

## <a name="retrieve-the-net-framework-version"></a><a name="retrieve_dotnet"></a>.NET Framework Sürümünü Al

Aşağıdaki kod örneği, sürüm bilgilerini içeren bir <xref:System.Environment.Version%2A> <xref:System.Version> nesneye işaretçi olan özellik ile şu anda yüklenen .NET Framework sürümünü nasıl belirleyeceklerini gösterir.

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

## <a name="retrieve-the-local-machine-name"></a><a name="retrieve_local"></a>Yerel Makine Adını Alma

Aşağıdaki kod örneği, yerel makine adının (ağda görünen bilgisayarın adı) alınmasını gösterir. Bunu, <xref:System.Environment> ad alanında <xref:System.Environment.MachineName%2A> tanımlanan dizeyi alarak başarabilirsiniz.

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

## <a name="retrieve-the-windows-version"></a><a name="retrieve_version"></a>Windows Sürümünü Alma

Aşağıdaki kod örneği, geçerli işletim sisteminin platform ve sürüm bilgilerinin nasıl alınabildiğini gösterir. Bu bilgiler <xref:System.Environment.OSVersion%2A?displayProperty=fullName> özellikte depolanır ve Windows'un sürümünü geniş terimlerle açıklayan bir <xref:System.Environment.Version%2A> numaralandırma ve işletim sisteminin tam oluşturmasını içeren bir nesneden oluşur.

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

## <a name="retrieve-time-elapsed-since-startup"></a><a name="retrieve_time"></a>Başlangıçtan Bu Yana Geçen Süreyi Al

Aşağıdaki kod örneği, Windows'un başlatılmasından bu yana geçen onay sayısının veya milisaniye sayısının nasıl belirlendiğini gösterir. Bu değer <xref:System.Environment.TickCount%2A?displayProperty=fullName> üyede depolanır ve 32 bitlik bir değer olduğundan, yaklaşık olarak her 24,9 günde bir sıfırlanır.

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

## <a name="store-text-in-the-clipboard"></a><a name="store_text"></a>Metni Panoda Depola

Aşağıdaki kod örneği, <xref:System.Windows.Forms.Clipboard> bir dize depolamak için <xref:System.Windows.Forms> ad alanında tanımlanan nesneyi kullanır. Bu nesne iki üye <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>işlev sağlar: ve . Veriler, <xref:System.Object> <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>''den türetilen herhangi bir nesne gönderilerek Pano'da depolanır.

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

## <a name="write-data-to-the-windows-registry"></a><a name="write_data"></a>Windows Kayıt Defterine Veri Yazma

Aşağıdaki kod örneği, <xref:Microsoft.Win32.Registry.CurrentUser> <xref:Microsoft.Win32.RegistryKey> **sınıfın Yazılım** anahtarına karşılık gelen yazılabilir bir örneğini oluşturmak için anahtarı kullanır. Yöntem <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> daha sonra yeni bir anahtar oluşturmak ve anahtar/değer çiftleri eklemek için kullanılır.

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

.NET Framework'u kullanarak kayıt defterine <xref:Microsoft.Win32.Registry> her <xref:Microsoft.Win32.RegistryKey> ikisi de <xref:Microsoft.Win32> ad alanında tanımlanan sınıfları ve sınıfları ile erişebilirsiniz. **Kayıt Defteri** sınıfı, <xref:Microsoft.Win32.RegistryKey> sınıfın statik örnekleri için bir kapsayıcıdır. Her örnek bir kök kayıt defteri düğümünü temsil eder. Örnekler <xref:Microsoft.Win32.Registry.ClassesRoot>, , <xref:Microsoft.Win32.Registry.CurrentConfig> <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, <xref:Microsoft.Win32.Registry.Users>ve .

## <a name="related-sections"></a>İlgili Bölümler

<xref:System.Environment>

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
