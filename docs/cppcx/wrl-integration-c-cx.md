---
title: "WRL tümleştirme (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 289c82a69ebc549d53e7b8ae49b6939200eb3aac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="wrl-integration-ccx"></a>WRL tümleştirme (C + +/ CX)
WRL koduyla serbestçe karıştırabilirsiniz [!INCLUDE[cppwrl](includes/cppwrl-md.md)] ([!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]) kodu. Aynı çeviri biriminde WRL tanıtıcı-için-nesnesiyle bildirilen nesneleri kullanabilirsiniz (`^`) gösterimi ve [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] akıllı işaretçisi (`ComPtr<T>`) gösterimi. Ancak, el ile dönüş değerleri işlemesi gerekir ve [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] HRESULT hata kodları ve WRL özel durumları.  
  
## <a name="includecppwrlshortincludescppwrl-short-mdmd-development"></a>[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]Geliştirme  
 Geliştirme ve kullanma hakkında daha fazla bilgi için [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] bileşenleri bkz [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod parçacığını WRL kullanarak gösterir ve [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] tüketmeye [!INCLUDE[wrt](includes/wrt-md.md)] sınıfları ve meta veri dosyasını inceleyin.  
>>>>>>> master
  
 Bir kod parçacığında alınan örnek [yapı Windows mağazası uygulamaları Forumu](http://social.msdn.microsoft.com/Forums/winappswithnativecode/thread/211ef583-db11-4e55-926b-6d9ab53dbdb4). Bu kod parçacığını yazarı aşağıdaki bildirimler ve stipulations sunar:  
  
1.  C++ yansıtacak şekilde belirli API'leri sunmaz [!INCLUDE[wrt](includes/wrt-md.md)] türleri, ancak Windows meta veri dosyaları (.winmd) bir tür için CLR meta veri dosyaları ile tamamen uyumlu. Windows sağlayan yeni meta veri bulma API'leri için belirli bir türde .winmd dosyasına almak için (RoGetMetaDataFile). Ancak, bir sınıfın örneği oluşturulamıyor için bu API'leri C++ geliştiricilere sınırlı kullanım durumdadır.  
  
2.  Derlenmiş kod sonra Runtimeobject.lib ve Rometadata.lib bağlayıcıya geçmesi gerekir.  
  
3.  Bu kod parçası olarak sunulan-değil. Doğru çalışması için beklenen olsa da, büyük olasılıkla hataları içerebilir.  
  
```  
  
#include <hstring.h>  
#include <cor.h>  
#include <rometadata.h>  
#include <rometadataresolution.h>  
#include <collection.h>  
  
namespace ABI_Isolation_Workaround {  
    #include <inspectable.h>  
    #include <WeakReference.h>  
}  
using namespace ABI_Isolation_Workaround;  
#include <wrl/client.h>  
  
using namespace Microsoft::WRL;  
using namespace Windows::Foundation::Collections;  
  
IVector<String^>^ GetTypeMethods(Object^);  
  
MainPage::MainPage()  
{  
    InitializeComponent();  
  
    Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/");  
    auto methods = GetTypeMethods(uri);  
  
    std::wstring strMethods;  
    std::for_each(begin(methods), end(methods), [&strMethods](String^ methodName) {  
        strMethods += methodName->Data();  
        strMethods += L"\n";  
    });  
  
    wprintf_s(L"%s\n", strMethods.c_str());  
}  
  
IVector<String^>^ GetTypeMethods(Object^ instance)  
{  
    HRESULT hr;  
    HSTRING hStringClassName;  
    hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD  
    if (FAILED(hr))  
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD  
    String^ className = reinterpret_cast<String^>(hStringClassName);   
  
    ComPtr<IMetaDataDispenserEx> metadataDispenser; ComPtr<IMetaDataImport2> metadataImport; hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf());  
    if (FAILED(hr))  
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD  
  
    HSTRING hStringFileName;  
    mdTypeDef typeDefToken;   
    hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken);  
    if (FAILED(hr))  
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD  
    String^ fileName = reinterpret_cast<String^>(hStringFileName);  
  
    HCORENUM hCorEnum = 0;  
    mdMethodDef methodDefs[2048];  
    ULONG countMethodDefs = sizeof(methodDefs);  
    hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs);  
    if (FAILED(hr))  
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD  
  
    wchar_t methodName[1024];  
    ULONG countMethodName;  
    std::wstring strMethods;  
    Vector<String^>^ retVal = ref new Vector<String^>();  
  
    for(int i = 0; i < countMethodDefs; ++i)  
    {  
        countMethodName = sizeof(methodName);  
        hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr);  
        if (SUCCEEDED(hr))  
        {  
            methodName[ countMethodName ] = 0;  
            retVal->Append(ref new String(methodName));  
        }  
    }  
    return retVal;  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diğer dilleri ile birlikte çalışma](interoperating-with-other-languages-c-cx.md)