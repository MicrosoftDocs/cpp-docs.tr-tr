---
description: ': WRL tümleştirmesi hakkında daha fazla bilgi edinin (C++/CX)'
title: WRL Tümleştirme (C++/CX)
ms.date: 01/22/2017
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
ms.openlocfilehash: ecf0bec03fedc0e860bb4f546d4ef067db681139
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287963"
---
# <a name="wrl-integration-ccx"></a>WRL Tümleştirme (C++/CX)

Windows Çalışma Zamanı C++ Şablon kitaplığı (WRL) kodu ile WRL Code 'u serbestçe karıştırabilirsiniz. Aynı çeviri biriminde, WRL Handle-to-Object ( `^` ) gösterimi ve WRL akıllı işaretçi () gösterimi ile tanımlanmış nesneleri kullanabilirsiniz `ComPtr<T>` . Ancak, dönüş değerlerini ve WRL HRESULT hata kodlarını ve WRL özel durumlarını el ile işlemeniz gerekir.

## <a name="wrl-development"></a>WRL geliştirme

WRL bileşenlerini yazma ve kullanma hakkında daha fazla bilgi için bkz. [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](./wrl/windows-runtime-cpp-template-library-wrl.md).

### <a name="example"></a>Örnek

Aşağıdaki kod parçacığı, Windows Çalışma Zamanı sınıfları tüketmek ve bir meta veri dosyasını incelemek için WRL ve WRL kullanımını gösterir.

Örnek, derleme Microsoft Store uygulamalar forumundaki bir kod parçacığı üzerinden alınır. Bu kod parçacığının yazarı aşağıdaki bildirimler ve stipula sağlar:

1. C++, Windows Çalışma Zamanı türlerini yansıtmak için belirli API 'Ler sağlamaz, ancak bir tür için Windows meta veri dosyaları (. winmd) CLR meta veri dosyalarıyla tamamen uyumludur. Windows, belirli bir tür için. winmd dosyasına ulaşmak üzere yeni meta veri bulma API 'Leri (RoGetMetaDataFile) sağlar. Ancak, bir sınıfı örnekleyemezsiniz, bu API 'Ler C++ geliştiricilerine sınırlı olarak kullanılır.

1. Kod derlendikten sonra, de Runtimeobject. lib ve Rometadata. lib ' i bağlayıcıya geçirmeniz gerekir.

1. Bu kod parçacığı olduğu gibi sunulur. Düzgün çalışması beklenirken, muhtemelen hata içerebilir.

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

[Diğer dillerle birlikte çalışma](interoperating-with-other-languages-c-cx.md)
