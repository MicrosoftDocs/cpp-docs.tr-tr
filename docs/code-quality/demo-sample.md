---
title: Kod analizi için örnek C++ projesi
description: Visual Studio'daki Microsoft C++ için kod analizi gözden geçirme de kullanılmak üzere örnek bir çözüm oluşturma.
ms.date: 04/14/2020
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: c2a1b8c80b7e7aebd1f1530c66ade5859b392028
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372054"
---
# <a name="sample-c-project-for-code-analysis"></a>Kod analizi için örnek C++ projesi

Aşağıdaki [yordamlar, Walkthrough: Analyze C/C++ kodunu niçin oluşturabileceğinizi](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md)gösterir. Yordamlar oluşturur:

- *CppDemo*adlı bir Görsel Stüdyo çözümü .

- *CodeKusurları*adlı statik bir kitaplık projesi.

- *Ek Açıklamalar*adlı statik bir kitaplık projesi.

Yordamlar ayrıca, statik kitaplıklar için üstbilgi ve *.cpp* dosyaları için kod sağlar.

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo çözümve CodeDefects projesini oluşturun

::: moniker range=">=vs-2019"

1. Visual Studio'u açın ve **yeni bir proje oluştur'u** seçin

1. Yeni **bir proje oluştur** iletişim kutusunda, dil filtresini **C++** olarak değiştirin.

1. **Windows Masaüstü Sihirbazı'nı** seçin ve **İleri** düğmesini seçin.

1. Yeni **proje sayfanızı Yapılandır'** da, **Proje adı** metin kutusuna *CodeDefects*girin.

1. Çözüm **adı** metin kutusuna *CppDemo'yu*girin.

1. **Oluştur**’u seçin.

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türünü** Statik **Kitaplık (.lib) olarak değiştirin.**

1. **Ek seçenekler**altında, **Boş proje'yi**seçin.

1. Çözüm ve proje oluşturmak için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="vs-2017"

1. Visual Studio'yu açın. Menü çubuğunda**Yeni** > **Proje** **yi seçin.** > 

1. Yeni **Proje** iletişim kutusunda **Visual C++** > **Windows Desktop'ı**seçin.

1. **Windows Masaüstü Sihirbazı'nı**seçin.

1. **Ad** metin kutusuna *CodeDefects*girin.

1. Çözüm **adı** metin kutusuna *CppDemo'yu*girin.

1. **Tamam'ı**seçin.

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türünü** Statik **Kitaplık (.lib) olarak değiştirin.**

1. **Ek seçenekler**altında, **Boş proje'yi**seçin.

1. Çözüm ve proje oluşturmak için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="vs-2015"

1. Visual Studio'yu açın. Menü çubuğunda**Yeni** > **Proje** **yi seçin.** > 

1. Yeni **Proje** iletişim kutusunda, **Şablonlar** > **Visual C++** > **Win32'yi**seçin.

1. **Win32 Konsol Uygulamasını**seçin.

1. **Ad** metin kutusuna *CodeDefects*girin.

1. Çözüm **adı** metin kutusuna *CppDemo'yu*girin.

1. **Tamam'ı**seçin.

1. **Win32 Uygulama Sihirbazı** iletişim kutusunda **İleri** düğmesini seçin.

1. Uygulama **türünü** **Statik kitaplık**olarak değiştirin.

1. **Ek seçenekler**altında, **önceden derlenmiş üstbilgi**nin seçilmi.

1. Çözümü ve projeyi oluşturmak için **Finish'i** seçin.

::: moniker-end

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>Üstbilgi ve kaynak dosyayı CodeDefects projesine ekleme

1. Çözüm Gezgini'nde **CodeDefects'i genişletin.**

1. **Üstbilgi Dosyaları**için bağlam menüsünü açmak için sağ tıklatın. **Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **Visual C++** > **Kodu'nu**seçin ve ardından **Üstbilgi Dosyası 'nı (.h)** seçin.

1. **Ad** edit kutusuna *Bug.h'yi*girin ve sonra **Ekle** düğmesini seçin.

1. *Bug.h*için düzenle penceresinde, içeriği seçin ve silin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *Hata.h* dosyasına yapıştırın.

    ```cpp
    #pragma once

    #include <windows.h>

    // Function prototypes
    bool CheckDomain(wchar_t const *);
    HRESULT ReadUserAccount();

    // These constants define the common sizes of the
    // user account information throughout the program
    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

1. Çözüm Gezgini'nde, **Kaynak Dosyalar**için bağlam menüsünü açmak için sağ tıklatın. **Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **C++ Dosyası (.cpp)** seçeneğini belirleyin.

1. **Ad** edit kutusuna *Bug.cpp'yi*girin ve sonra **Ekle** düğmesini seçin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *Hata.cpp* dosyasına yapıştırın.

    ```cpp
    #include "Bug.h"

    // the user account
    wchar_t g_userAccount[USER_ACCOUNT_LEN] = { L"domain\\user" };
    int len = 0;

    bool CheckDomain(wchar_t const* domain)
    {
        return (wcsnlen_s(domain, USER_ACCOUNT_LEN) > 0);
    }

    HRESULT ReadUserAccount()
    {
        return S_OK;
    }

    bool ProcessDomain()
    {
        wchar_t* domain = new wchar_t[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount())
        {
            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for (len = 0; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != L'\0'); len++)
            {
                if (g_userAccount[len] == L'\\')
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if ((len = ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete[] domain;
                return false;
            }
            else
            {
                domain[len] = L'\0';
            }
            // Process domain string
            bool result = CheckDomain(domain);

            delete[] domain;
            return result;
        }
        return false;
    }

    int path_dependent(int n)
    {
        int i;
        int j;
        if (n == 0)
            i = 1;
        else
            j = 1;
        return i + j;
    }
    ```

1. Menü çubuğunda**Tümlerini Kaydet'i** **seçin.** > 

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Ek Açıklamalar projesini ekleyin ve statik kitaplık olarak yapılandırın

::: moniker range=">=vs-2019"

1. Çözüm Gezgini'nde bağlam menüsünü açmak için **CppDemo'ya** sağ tıklayın. **Yeni Proje** **Ekle'yi** > seçin.

1. Yeni **proje** iletişim kutusu ekle kutusunda **Windows Desktop Wizard'ı**seçin ve ardından **Sonraki** düğmesini seçin.

1. Yeni **proje sayfanızı Yapılandır' da,** **Proje adı** metin kutusunda Ek *Açıklamalar*girin ve sonra **Oluştur'u**seçin.

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türünü** Statik **Kitaplık (.lib) olarak değiştirin.**

1. **Ek seçenekler**altında, **Boş proje'yi**seçin.

1. Projeyi oluşturmak için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="vs-2017"

1. Çözüm Gezgini'nde bağlam menüsünü açmak için **CppDemo'ya** sağ tıklayın. **Yeni Proje** **Ekle'yi** > seçin.

1. Yeni **Proje Ekle** iletişim kutusunda **Visual C++** > **Windows Desktop'ı**seçin.

1. **Windows Masaüstü Sihirbazı'nı**seçin.

1. **Ad** metin kutusuna Ek *Açıklamalar*girin ve sonra **Tamam'ı**seçin.

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türünü** Statik **Kitaplık (.lib) olarak değiştirin.**

1. **Ek seçenekler**altında, **Boş proje'yi**seçin.

1. Projeyi oluşturmak için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="vs-2015"

1. Çözüm Gezgini'nde bağlam menüsünü açmak için **CppDemo'ya** sağ tıklayın. **Yeni Proje** **Ekle'yi** > seçin.

1. Yeni **Proje Ekle** iletişim kutusunda **Visual C++** > **Win32'yi**seçin.

1. **Win32 Konsol Uygulamasını**seçin.

1. **Ad** metin kutusuna *Ek Açıklamalar*girin.

1. **Tamam'ı**seçin.

1. **Win32 Uygulama Sihirbazı** iletişim kutusunda **İleri** düğmesini seçin.

1. Uygulama **türünü** **Statik kitaplık**olarak değiştirin.

1. **Ek seçenekler**altında, **önceden derlenmiş üstbilgi**nin seçilmi.

1. Projeyi oluşturmak için **Finish'i** seçin.

::: moniker-end

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>Üstbilgi dosyasını ve kaynak dosyasını Ek Açıklamalar projesine ekleme

1. Çözüm Gezgini'nde Ek **Açıklamaları genişletin.**

1. **Ek Açıklamalar**altında **Üstbilgi Dosyaları** için bağlam menüsünü açmak için sağ tıklatın. **Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **Visual C++** > **Kodu'nu**seçin ve ardından **Üstbilgi Dosyası 'nı (.h)** seçin.

1. **Ad** edit kutusuna, *ek açıklamalar.h*'yi girin ve sonra **Ekle** düğmesini seçin.

1. *Ek açıklamalar.h*için düzenle penceresinde, içeriği seçin ve silin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *ek açıklamalar.h* dosyasına yapıştırın.

    ```cpp
    #pragma once
    #include <sal.h>

    struct LinkedList
    {
        struct LinkedList* next;
        int data;
    };

    typedef struct LinkedList LinkedList;

    _Ret_maybenull_ LinkedList* AllocateNode();
    ```

1. Çözüm Gezgini'nde, **Ek Açıklamalar**altında **Kaynak Dosyalar** için bağlam menüsünü açmak için sağ tıklatın. **Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **C++ Dosyası (.cpp)** seçeneğini belirleyin.

1. **Ad** edit kutusuna ek *açıklamalar.cpp*girin ve sonra **Ekle** düğmesini seçin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *ek açıklamalar.cpp* dosyasına yapıştırın.

    ```cpp
    #include "annotations.h"
    #include <malloc.h>

    _Ret_maybenull_ LinkedList* AllocateNode()
    {
        LinkedList* result = static_cast<LinkedList*>(malloc(sizeof(LinkedList)));
        return result;
    }

    LinkedList* AddTail(LinkedList* node, int value)
    {
        // finds the last node
        while (node->next != nullptr)
        {
            node = node->next;
        }

        // appends the new node
        LinkedList* newNode = AllocateNode();
        newNode->data = value;
        newNode->next = 0;
        node->next = newNode;

        return newNode;
    }
    ```

1. Menü çubuğunda**Tümlerini Kaydet'i** **seçin.** > 

Çözüm artık tamamlandı ve hatasız inşa etmelidir.

::: moniker range="vs-2017"

> [!NOTE]
> Visual Studio 2017'de IntelliSense `E1097 unknown attribute "no_init_all"` motorunda sahte bir uyarı görebilirsiniz. Bu uyarıyı güvenle yoksayabilirsiniz.

::: moniker-end
