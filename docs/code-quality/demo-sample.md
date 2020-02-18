---
title: Kod C++ analizi için örnek proje
ms.date: 11/04/2016
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: 1966e9cec5825ae37728bbf28c0f21ff4eed62fc
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418825"
---
# <a name="sample-c-project-for-code-analysis"></a>Kod C++ analizi için örnek proje

Aşağıdaki yordamlarda Izlenecek yol için örneğin nasıl oluşturulacağı gösterilmektedir [: hatalar Için CC++ /kod çözümleme](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md). Şu yordamları oluşturun:

- CppDemo adlı bir Visual Studio çözümü.

- Codearızaları adlı bir statik kitaplık projesi.

- Ek açıklamalar adlı bir statik kitaplık projesi.

Yordamlar ayrıca statik kitaplıklar için üst bilgi ve *. cpp* dosyaları için kod sağlar.

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo çözümü ve Codekusurları projesi oluşturma

1. Visual Studio 'Yu açın ve **Yeni proje oluştur** ' u seçin

1. Dil filtresini Değiştir**C++**

1. **Boş proje** ' yi seçin ve **İleri** ' ye tıklayın

1. **Proje adı** metin kutusuna **codekusurlarını** yazın

1. **Çözüm adı** metin kutusuna **CppDemo** yazın

1. **Oluştur**'a tıklayın

## <a name="configure-the-codedefects-project-as-a-static-library"></a>Codekusurları projesini statik kitaplık olarak yapılandırma

1. Çözüm Gezgini, **Codekusurları** ' na sağ tıklayın ve ardından **Özellikler**' e tıklayın.

1. **Yapılandırma özellikleri** ' ni genişletin ve ardından **genel**' e tıklayın.

1. **Genel** listesinde, **yapılandırma türünü** **statik kitaplık (. lib)** olarak değiştirin.

1. **Gelişmiş** listede **hedef dosya uzantısını** **. lib** olarak değiştirin

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>Üstbilgi ve kaynak dosyayı Codekusurları projesine ekleyin

1. Çözüm Gezgini, **kod hataları**' nı genişletin, **üst bilgi dosyaları**' na sağ tıklayın, **Ekle**' ye ve ardından **Yeni öğe**' ye tıklayın

1. **Yeni öğe Ekle** iletişim kutusunda, **kod**' a ve ardından **üstbilgi dosyası (. h)** ' na tıklayın.

1. **Ad** kutusuna **Bug. h** yazın ve ardından **Ekle**' ye tıklayın.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *hata. h* dosyasına yapıştırın.

    ```cpp
    #pragma once

    #include <windows.h>

    // These functions are consumed by the sample
    // but are not defined. This project cannot be linked!
    bool CheckDomain(LPCTSTR);
    HRESULT ReadUserAccount();

    // These constants define the common sizes of the
    // user account information throughout the program
    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

1. Çözüm Gezgini, **kaynak dosyalar**' a sağ tıklayın, **Yeni**' nin üzerine gelin ve ardından **Yeni öğe**' ye tıklayın.

1. **Yeni öğe Ekle** iletişim kutusunda  **C++ dosya (. cpp)** öğesine tıklayın.

1. **Ad** kutusuna **Bug. cpp** yazın ve ardından **Ekle**' ye tıklayın.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *hata. cpp* dosyasına yapıştırın.

    ```cpp
    #include "Bug.h"

    // the user account
    TCHAR g_userAccount[USER_ACCOUNT_LEN] = {};
    int len = 0;

    bool ProcessDomain()
    {
        TCHAR* domain = new TCHAR[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount())
        {
            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for (len = 0; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != L'\0'); len++)
            {
                if (g_userAccount[len] == '\\')
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if ((len = ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete[] domain;
                return false;
            }
            else
            {
                domain[len] = '\0';
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

1. **Dosya** menüsüne tıklayın ve ardından **Tümünü Kaydet**' e tıklayın.

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Ek açıklamalar projesini ekleme ve statik kitaplık olarak yapılandırma

1. Çözüm Gezgini, **CppDemo**' e tıklayın, **Ekle**' nin üzerine gelin ve ardından **Yeni proje**' ye tıklayın.

1. **Yeni Proje Ekle** iletişim kutusunda dil filtresini olarak **C++** değiştirip **boş proje** ' yi seçin ve ardından **İleri**' ye tıklayın.

1. **Proje adı** metin kutusuna **ek açıklamalar**yazın ve ardından **Oluştur**' a tıklayın.

1. Çözüm Gezgini, **ek açıklamalar** ' a sağ tıklayın ve ardından **Özellikler**' e tıklayın.

1. **Yapılandırma özellikleri** ' ni genişletin ve ardından **genel**' e tıklayın.

1. **Genel** listesinde **yapılandırma türünü**değiştirin ve ardından **statik kitaplık (. lib)** öğesine tıklayın.

1. **Gelişmiş** listede, **hedef dosya uzantısı**' nın yanındaki sütundaki metni seçin ve **. lib**yazın.

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>Üst bilgi dosyasını ve kaynak dosyayı ek açıklamalar projesine ekleyin

1. Çözüm Gezgini, **ek açıklamalar**' ı genişletin, **üstbilgi dosyaları**' na sağ tıklayın, **Ekle**' ye ve ardından **Yeni öğe**' ye tıklayın.

1. **Yeni öğe Ekle** Iletişim kutusunda **üst bilgi dosyası (. h)** seçeneğine tıklayın.

1. **Ad** kutusuna, **ek açıklama. h** yazın ve ardından **Ekle**' ye tıklayın.

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

1. Çözüm Gezgini, **kaynak dosyalar**' a sağ tıklayın, **Yeni**' nin üzerine gelin ve ardından **Yeni öğe**' ye tıklayın.

1. **Yeni öğe Ekle** iletişim kutusunda, **kod** ' a ve ardından  **C++ dosya (. cpp)** ' ye tıklayın.

1. **Ad** kutusuna, **ek açıklama. cpp** yazın ve ardından **Ekle**' ye tıklayın.

1. Aşağıdaki kodu kopyalayın ve düzenleyicideki *ek açıklama. cpp* dosyasına yapıştırın.

    ```cpp
    #include "annotations.h"

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

1. **Dosya** menüsüne tıklayın ve ardından **Tümünü Kaydet**' e tıklayın.

Çözüm artık tamamlanmıştır ve hatasız bir şekilde oluşturulmalıdır.
