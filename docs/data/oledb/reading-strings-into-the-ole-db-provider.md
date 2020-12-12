---
description: 'Hakkında daha fazla bilgi edinin: OLE DB sağlayıcısına dizeler okuma'
title: Dizeleri OLE DB Sağlayıcısına Okuma
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: 5df8812d5589dd457684bf5e36a8a49f798f99aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286637"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Dizeleri OLE DB Sağlayıcısına Okuma

`CCustomRowset::Execute`İşlevi bir dosya açar ve dizeleri okur. Tüketici, [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85))' i çağırarak dosya adını sağlayıcıya geçirir. Sağlayıcı dosya adını alır ve üye değişkeninde depolar `m_strCommandText` . `Execute` dosya adını öğesinden okur `m_strCommandText` . Dosya adı geçersizse veya dosya kullanılamıyorsa `Execute` bir hata döndürür. Aksi takdirde, dosyayı açar ve `fgets` dizeleri almak için çağırır. Okuduğu her bir dize kümesi için, `Execute` Kullanıcı kaydının bir örneğini oluşturur ( `CCustomWindowsFile` [OLE DB sağlayıcıda dizeleri depolamadan](../../data/oledb/storing-strings-in-the-ole-db-provider.md)değiştirilir) ve bir diziye koyar.

Dosya açılamadığı takdirde `Execute` DB_E_NOTABLE döndürmelidir. Bunun yerine E_FAIL döndürürse, sağlayıcı birçok tüketici ile çalışmaz ve OLE DB [uygunluk testlerini](../../data/oledb/testing-your-provider.md)geçirmez.

## <a name="example"></a>Örnek

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
{
public:
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
    {
        enum {
            sizeOfBuffer = 256,
            sizeOfFile = MAX_PATH
        };
        USES_CONVERSION;
        FILE* pFile = NULL;
        TCHAR szString[sizeOfBuffer];
        TCHAR szFile[sizeOfFile];
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
            }

            am.dwBookmark = ++cFiles;
            if (!m_rgRowData.Add(am))
            {
                ATLTRACE("Couldn't add data to array");
                fclose(pFile);
                return E_FAIL;
            }
        }

        if (pcRowsAffected != NULL)
            *pcRowsAffected = cFiles;
        return S_OK;
    }
};
```

Bu tamamlandığında, sağlayıcınız derlemek ve çalıştırmak için hazırlanmalıdır. Sağlayıcıyı test etmek için eşleşen işlevselliğe sahip bir tüketiciye ihtiyacınız vardır. [Basit bir tüketici uygulamak](../../data/oledb/implementing-a-simple-consumer.md) , böyle bir test tüketicisinin nasıl oluşturulacağını gösterir. Test tüketicisini sağlayıcıyla çalıştırın ve test tüketicisinin sağlayıcıdan uygun dizeleri aldığını doğrulayın.

Sağlayıcınızı başarıyla test ettiğinizde, Ek arabirimler uygulayarak işlevselliğini geliştirmek isteyebilirsiniz. [Basit Read-Only sağlayıcıyı geliştirmeyle](../../data/oledb/enhancing-the-simple-read-only-provider.md)bir örnek gösterilmektedir.

## <a name="see-also"></a>Ayrıca bkz.

[Basit Read-Only sağlayıcıyı uygulama](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
