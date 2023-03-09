[![Tests](https://img.shields.io/badge/Tests-GitHub%20Actions-blue)](https://github.com/Zemantic/ckanext-sldata_theme/actions)

# c-Kang SL Open Data Portal Theme

![Cang](https://i.imgur.com/rc6NBNY.jpg)

The CKAN theme for the open data portal of the Ministry of Health Sri Lanka

![Data portal](https://i.imgur.com/3jfSpnK.png)

## Requirements

For full functionality of the theme, CKAN CMS has to be installed together with theme, see https://github.com/zemantic/ckan-cms

## Compatibility with core CKAN versions:

| CKAN version | Compatible? |
| ------------ | ----------- |
| 2.9.7        | tested      |
| 2.10         | not tested  |

## Installation

**TODO:** Add any additional install steps to the list below.
For example installing any non-Python dependencies or adding any required
config settings.

To install ckanext-sldata_theme:

1.  Activate your CKAN virtual environment, for example:

    . /usr/lib/ckan/default/bin/activate

2.  Clone the source and install it on the virtualenv

    `

        git clone https://github.com/Zemantic/ckanext-sldata_theme.git

        cd ckanext-sldata_theme

        pip install -e .

        pip install -r requirements.txt

    `

3.  Add `sldata_theme` to the `ckan.plugins` setting in your CKAN
    config file (by default the config file is located at
    `/etc/ckan/default/ckan.ini`).

4.  Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu:

    sudo supervisorctrl restart all

## Config settings

None at present

**TODO:** Document any optional config settings here. For example:

    # The minimum number of hours to wait before re-checking a resource
    # (optional, default: 24).
    ckanext.sldata_theme.some_setting = some_default_value

## Developer installation

To install ckanext-sldata_theme for development, activate your CKAN virtualenv and
do:

    git clone https://github.com/Zemantic/ckanext-sldata_theme.git
    cd ckanext-sldata_theme
    python setup.py develop
    pip install -r dev-requirements.txt

## Tests

To run the tests, do:

    pytest --ckan-ini=test.ini

## Releasing a new version of ckanext-sldata_theme

If c
kanext-sldata_theme should be available on PyPI you can follow these steps to publish a new version:

1.  Update the version number in the `setup.py` file. See [PEP 440](http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers) for how to choose version numbers.

2.  Make sure you have the latest version of necessary packages:

    pip install --upgrade setuptools wheel twine

3.  Create a source and binary distributions of the new version:

        python setup.py sdist bdist_wheel && twine check dist/*

    Fix any errors you get.

4.  Upload the source distribution to PyPI:

    twine upload dist/\*

5.  Commit any outstanding changes:

    git commit -a
    git push

6.  Tag the new release of the project on GitHub with the version number from
    the `setup.py` file. For example if the version number in `setup.py` is
    0.0.1 then do:

        git tag 0.0.1
        git push --tags

## License

[AGPL](https://www.gnu.org/licenses/agpl-3.0.en.html)
