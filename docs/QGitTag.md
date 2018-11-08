# QGitRelease

The **QGitRelease** class provides information about releases from GitHub.

## Content

* [Public Types](#public-types)
* [Public Functions](#public-functions)
* [Signals](#signals)
* [Member Types Documentation](#member-types-documentation)
* [Member Functions Documentation](#member-functions-documentation)

## Public Types

| Type | Name                                                                    |
|-----:|:------------------------------------------------------------------------|
| enum | [**RequestError**](#request-error) { NoError, NetworkError, NoRelease } |

## Public Functions

| Return type        | Data member                                                                       |
|-------------------:|:----------------------------------------------------------------------------------|
|                    | [**QGitRelease**(QObject *parent = nullptr)](#constructor)                        |
| void               | [**get**(const QString &owner, const QString &repo, int number = 0)](#get)        |
| QString            | [**name**()](#name)                                                               |
| QString            | [**tagName**()](#tag-name)                                                        |
| QString            | [**body**()](#body)                                                               |
| QUrl               | [**url**()](#url)                                                                 |
| QUrl               | [**tarUrl**()](#tar-url)                                                          |
| QUrl               | [**zipUrl**()](#zip-url)                                                          |
| QList\<QGitAsset\> | [**assets**()](#assets)                                                           |
| int                | [**asset**(const QString &contentType)](#asset)                                   |
| QDateTime          | [**createdAt**()](#created-at)                                                    |
| QDateTime          | [**publishedAt**()](#published-at)                                                |
| int                | [**id**()](#id)                                                                   |
| bool               | [**draft**()](#draft)                                                             |
| bool               | [**prerelease**()](#prerelease)                                                   |
| RequestError       | [**error**()](#error)                                                             |
| QString            | [**errorName**()](#error-name)                                                    |

## Signals

| void | [*tagReceived**()](#tag-received) |

## Member Type Documentation

### <a id='request-error'/> enum QGitRelease::RequestError

Indicates all possible error conditions found during the requesting release

| Constant                             | Value | Description                                                  |
|-------------------------------------:|:-----:|:-------------------------------------------------------------|
| QOnlineTranslator::NoError           | 0     | No error condition	                                          |
| QOnlineTranslator::NetworkError      | 1     | Network error                                                |
| QOnlineTranslator::NoRelease         | 2     | There is no release with the specified number                |

## Member Function Documentation

### <a id='constructor'/> QGitRelease::QGitRelease(*const QString &owner, const QString &repo, int number = 0*)
Constructs an empty QGitRelease with parent object *parent*.
___

### <a id='tag-received'/> signal QGitRelease::tagReceived()
This signal is emitted when the reply has finished processing and parsed tag data.
___

### <a id='get'/> QGitRelease::get(*const QString &owner, const QString &repo, int number = 0*)
Query information about the release of the *number* from the *repo* of *owner*. 0 is the last release.
___

### <a id='name'/> [QString](http://doc.qt.io/qt-5/qstring.html "Qt Documentation") QGitRelease::name()
Returns the release name.
___

### <a id='tag-name'/> [QString](http://doc.qt.io/qt-5/qstring.html "Qt Documentation") QGitRelease::tagName()
Returns the release tag name that usually contains the version.
___

### <a id='body'/> [QString](http://doc.qt.io/qt-5/qstring.html "Qt Documentation") QGitRelease::body()
Returns the release body that usually contains the changelog.
___

### <a id='url'/> [QUrl](https://doc.qt.io/qt-5/qurl.html "Qt Documentation") QGitRelease::url()
Returns a link to the page of this release, which can be opened in the browser.
___

### <a id='tar-url'/> [QUrl](https://doc.qt.io/qt-5/qurl.html "Qt Documentation") QGitRelease::tarUrl()
Returns a link to the source tarball.
___

### <a id='zip-url'/> [QUrl](https://doc.qt.io/qt-5/qurl.html "Qt Documentation") QGitRelease::zipUrl()
Returns a link to the source zipball.
___

### <a id='assets'/> [QList](http://doc.qt.io/qt-5/qlist.html "Qt Documentation")<[QGitAsset](QGitAsset.md "Class documentation")> QGitRelease::assets()
Returns the release assets represented by [QGitAsset](QGitAsset.md "Class documentation").
___

### <a id='asset'/> int QGitRelease::asset(*const QString &contentType*)
Returns the asset number with the corresponding *contentType*. If such an asset is not found, returns -1.
___

### <a id='created-at'/> [QDateTime](https://doc.qt.io/qt-5/qdatetime.html "Qt Documentation") QGitRelease::createdAt()
Returns the creation time of the last commit on which the release is based.
___

### <a id='published-at'/> [QDateTime](https://doc.qt.io/qt-5/qdatetime.html "Qt Documentation") QGitRelease::publishedAt()
Returns the release publication time.
___

### <a id='id'/> int QGitRelease::id()
Returns the release identifier.
___

### <a id='draft'/> int QGitRelease::draft()
Returns *true* if the release is a draft, otherwise returns *false*.
___

### <a id='prerelease'/> int QGitRelease::prerelease()
Returns *true* if the release is marked as a pre-release, otherwise returns *false*.
___

### <a id='error'/> int QGitRelease::error()
Returns the error that was found during the processing of last release request. If no error was found, returns *NoError*.
___

### <a id='error-name'/> int QGitRelease::errorName()
Returns a human-readable description of the last request error that occurred.
___