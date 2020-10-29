---
title: Kod analizi için örnek C++ projesi
description: Visual Studio 'da Microsoft C++ için kod analizi kılavuznda kullanılmak üzere örnek bir çözüm oluşturma.
ms.date: 04/14/2020
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: dd4fe67c05200ccc2865bc7c48b1f5047d77565e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924625"
---
# <a name="sample-c-project-for-code-analysis"></a>Kod analizi için örnek C++ projesi

Aşağıdaki yordamlarda Izlenecek yol için örneğin nasıl oluşturulacağı gösterilmektedir [: hatalar Için C/C++ kodunu analiz etme](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md). Şu yordamları oluşturun:

- *CppDemo* adlı bir Visual Studio çözümü.

- *Codearızaları* adlı bir statik kitaplık projesi.

- *Ek açıklamalar* adlı bir statik kitaplık projesi.

Yordamlar ayrıca statik kitaplıklar için üst bilgi ve *. cpp* dosyaları için kod sağlar.

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo çözümü ve Codekusurları projesi oluşturma

::: moniker range=">=msvc-160"

1. Visual Studio 'Yu açın ve **Yeni proje oluştur** ' u seçin

1. **Yeni proje oluştur** iletişim kutusunda dil filtresini **C++** olarak değiştirin.

1. **Windows Masaüstü Sihirbazı** ' nı seçin ve **İleri** düğmesini seçin.

1. **Yeni projenizi yapılandırın** sayfasında, **Proje adı** metin kutusuna *codekusurlarını* girin.

1. **Çözüm adı** metin kutusuna *CppDemo* yazın.

1. **Oluştur** ' a tıklayın.

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türünü** **statik kitaplık (. lib)** olarak değiştirin.

1. **Ek seçenekler** altında **boş proje** ' yi seçin.

1. Çözümü ve projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="msvc-150"

1. Visual Studio'yu açın. Menü çubuğunda **Dosya**  >  **Yeni**  >  **Proje** ' yi seçin.

1. **Yeni proje** iletişim kutusunda **Visual C++** > **Windows Masaüstü** Visual C++ ' ni seçin.

1. **Windows Masaüstü Sihirbazı** ' nı seçin.

1. **Ad** metin kutusuna *codekusurlarını* girin.

1. **Çözüm adı** metin kutusuna *CppDemo* yazın.

1. **Tamam ' ı** seçin.

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türünü** **statik kitaplık (. lib)** olarak değiştirin.

1. **Ek seçenekler** altında **boş proje** ' yi seçin.

1. Çözümü ve projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="msvc-140"

1. Visual Studio'yu açın. Menü çubuğunda **Dosya**  >  **Yeni**  >  **Proje** ' yi seçin.

1. **Yeni proje** iletişim kutusunda, **Templates** > **Visual C++** > **Win32** Visual C++ Şablonlar ' ı seçin.

1. **Win32 konsol uygulaması** ' nı seçin.

1. **Ad** metin kutusuna *codekusurlarını* girin.

1. **Çözüm adı** metin kutusuna *CppDemo* yazın.

1. **Tamam ' ı** seçin.

1. **Win32 uygulama Sihirbazı** Iletişim kutusunda **İleri** düğmesini seçin.

1. **Uygulama türünü** **statik kitaplık** olarak değiştirin.

1. **Ek seçenekler** altında, **önceden derlenmiş üstbilginin** seçimini kaldırın.

1. Çözümü ve projeyi oluşturmak için **son** ' a tıklayın.

::: moniker-end

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>Üstbilgi ve kaynak dosyayı Codekusurları projesine ekleyin

1. Çözüm Gezgini, **kod hataları** ' nı genişletin.

1. **Üst bilgi dosyaları** için bağlam menüsünü açmak için sağ tıklayın. **Add**  >  **Yeni öğe** Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda **Visual C++**  >  **kodu** ' nu seçin ve ardından **üst bilgi dosyası (. h)** öğesini seçin.

1. **Ad** düzenleme kutusunda *Bug. h* girin ve sonra **Ekle** düğmesini seçin.

1. *Hata. h* için düzenleme penceresinde, içeriği seçin ve silin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *hata. h* dosyasına yapıştırın.

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

1. Çözüm Gezgini ' de, **kaynak dosyalarının** bağlam menüsünü açmak için sağ tıklayın. **Add**  >  **Yeni öğe** Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, **C++ dosyası (. cpp)** öğesini seçin.

1. **Ad** düzenleme kutusunda *Bug. cpp* girin ve sonra **Ekle** düğmesini seçin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *hata. cpp* dosyasına yapıştırın.

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

1. Menü çubuğunda **Dosya**  >  **Tümünü Kaydet** ' i seçin.

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Ek açıklamalar projesini ekleme ve statik kitaplık olarak yapılandırma

::: moniker range=">=msvc-160"

1. Çözüm Gezgini, bağlam menüsünü açmak için **CppDemo** öğesine sağ tıklayın. **Add**  >  **Yeni proje** Ekle öğesini seçin.

1. **Yeni Proje Ekle** iletişim kutusunda, **Windows Masaüstü Sihirbazı** ' nı seçin ve ardından **İleri** düğmesini seçin.

1. **Yeni projenizi yapılandırın** sayfasında, **Proje adı** metin kutusuna *ek açıklamalar* girin ve ardından **Oluştur** ' u seçin.

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türünü** **statik kitaplık (. lib)** olarak değiştirin.

1. **Ek seçenekler** altında **boş proje** ' yi seçin.

1. Projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="msvc-150"

1. Çözüm Gezgini, bağlam menüsünü açmak için **CppDemo** öğesine sağ tıklayın. **Add**  >  **Yeni proje** Ekle öğesini seçin.

1. **Yeni Proje Ekle** iletişim kutusunda **Visual C++** > **Windows Masaüstü** Visual C++ ' yi seçin.

1. **Windows Masaüstü Sihirbazı** ' nı seçin.

1. **Ad** metin kutusuna *ek açıklamalar* yazın ve ardından **Tamam** ' ı seçin.

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türünü** **statik kitaplık (. lib)** olarak değiştirin.

1. **Ek seçenekler** altında **boş proje** ' yi seçin.

1. Projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="msvc-140"

1. Çözüm Gezgini, bağlam menüsünü açmak için **CppDemo** öğesine sağ tıklayın. **Add**  >  **Yeni proje** Ekle öğesini seçin.

1. **Yeni Proje Ekle** iletişim kutusunda Win32 Visual C++ seçin **Visual C++** > **Win32** .

1. **Win32 konsol uygulaması** ' nı seçin.

1. **Ad** metin kutusuna *ek açıklamalar* girin.

1. **Tamam ' ı** seçin.

1. **Win32 uygulama Sihirbazı** Iletişim kutusunda **İleri** düğmesini seçin.

1. **Uygulama türünü** **statik kitaplık** olarak değiştirin.

1. **Ek seçenekler** altında, **önceden derlenmiş üstbilginin** seçimini kaldırın.

1. Projeyi oluşturmak için **son** ' a tıklayın.

::: moniker-end

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>Üst bilgi dosyasını ve kaynak dosyayı ek açıklamalar projesine ekleyin

1. Çözüm Gezgini ' de, **ek açıklamalar** ' ı genişletin.

1. **Ek açıklamalar** altında **üstbilgi dosyalarının** bağlam menüsünü açmak için sağ tıklayın. **Add**  >  **Yeni öğe** Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda **Visual C++**  >  **kodu** ' nu seçin ve ardından **üst bilgi dosyası (. h)** öğesini seçin.

1. **Ad** düzenleme kutusunda, *ek açıklama. h* girin ve sonra **Ekle** düğmesini seçin.

1. *Ek açıklamalar. h* için düzenleme penceresinde, içeriği seçin ve silin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *ek açıklamalar. h* dosyasına yapıştırın.

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

1. Çözüm Gezgini ' de, **ek açıklamalar** altındaki **kaynak dosyaları** için bağlam menüsünü açmak için sağ tıklayın. **Add**  >  **Yeni öğe** Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, **C++ dosyası (. cpp)** öğesini seçin.

1. **Ad** düzenleme kutusunda, *ek açıklama. cpp* girin ve sonra **Ekle** düğmesini seçin.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *ek açıklama. cpp* dosyasına yapıştırın.

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

1. Menü çubuğunda **Dosya**  >  **Tümünü Kaydet** ' i seçin.

Çözüm artık tamamlanmıştır ve hatasız bir şekilde oluşturulmalıdır.

::: moniker range="msvc-150"

> [!NOTE]
> Visual Studio 2017 ' de, IntelliSense altyapısında bir çok değerli uyarı görebilirsiniz `E1097 unknown attribute "no_init_all"` . Bu uyarıyı güvenle yoksayabilirsiniz.

::: moniker-end
