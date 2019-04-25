---
title: WRL tümleştirme (C++/CX)
ms.date: 01/22/2017
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
ms.openlocfilehash: a3c8b824d2cd932a7d284804f3f28781654045e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62304156"
---
# <a name="wrl-integration-ccx"></a>WRL tümleştirme (C++/CX)

Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kod WRL koduyla serbestçe karıştırabilirsiniz. WRL tanıtıcı nesne ile bildirilen nesneler aynı çeviri biriminde kullanabilirsiniz (`^`) Akıllı işaretçi gösterimini ve WRL (`ComPtr<T>`) gösterimi. Ancak, el ile dönüş değerleri ve WRL HRESULT hata kodları ve WRL özel durumlarını işlemelidir.

## <a name="wrl-development"></a>WRL geliştirme

Yazma ve WRL bileşenlerinin kullanma hakkında daha fazla bilgi için bkz. [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

### <a name="example"></a>Örnek

Aşağıdaki kod parçacığı, Windows çalışma zamanı sınıflar kullanma ve bir meta veri dosyasını incelemek için WRL ve WRL'ı kullanmayı gösterir.

Örnek bir kod parçacığı oluşturma Microsoft Store uygulamaları forumdaki alınır. Bu kod parçacığı yazarının, aşağıdaki sorumluluk reddi ve stipulations sunar:

1. C++ Windows çalışma zamanı türlerini yansıtacak şekilde belirli API'lar sağlamaz, ancak Windows meta veri (.winmd) bir tür için CLR meta veri dosyaları ile tamamen uyumlu dosyalarıdır. Windows sağlayan yeni meta veri bulma API'ları (RoGetMetaDataFile verilen tür için .winmd dosyası almak için). Ancak, bir sınıfın örneği oluşturulamıyor çünkü bu API'leri sınırlı kullanım C++ geliştiricileri için uygulanır.

1. Kod derlendikten sonra Runtimeobject.lib ve Rometadata.lib bağlayıcıya geçmesi gerekir.

1. Bu kod parçacığı olarak sunulan-olduğu. Düzgün çalışması beklenir, ancak muhtemelen hataları içerebilir.

```cpp
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

    for (int i = 0; i < countMethodDefs; ++i)
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

## <a name="see-also"></a>Ayrıca bkz.

[Diğer Dillerle Birlikte Çalışma](interoperating-with-other-languages-c-cx.md)
